---
title: "Optimizing and Benchmarking GPU Collective Communication of PyLops-MPI with NCCL"
subtitle: "GPU-to-GPU Communication in PyLops-MPI for Large-scale Inverse Problems with Nvidia's NCCL" 
summary:
authors: 
  - tharitt 
tags: ["osre25", "gsoc25","lbl","PyLops-MPI"]
categories: ["High-performance Computing", "GPU", "NCCL", "Parallel Programming"]
date: 2025-07-23
lastmod: 2025-07-23
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "Center"
  preview_only: false
---

# Enabling NCCL GPU-GPU Communication in PyLops-MPI - Google Summer of Code Project (2025) - Part 2

Hello all! 👋 This is Tharit again. I want to share this blog post about my Part 2 of Google Summer of Code projects. In case you miss it, you can take a look at [Part1](https://ucsc-ospo.github.io/report/osre25/lbl/pylops-mpi/20250723-tharit/) as well. Without further introduction, these following supports were added since last time.


- ### Complex Number Support [PR #148](https://github.com/PyLops/pylops-mpi/pull/148)
_Between this PR and the previous PR, there are lots of debugging and testing to make sure that all existing `MPILinearOperator` works under NCCL as they do with `mpi4py` PR [#141](https://github.com/PyLops/pylops-mpi/pull/141), [#142](https://github.com/PyLops/pylops-mpi/pull/142) [#145](https://github.com/PyLops/pylops-mpi/pull/145)_

Most of the PyLops-MPI users are scientists and engineers working on the scientific problems - and most of the scientific problem involves complex numbers (Fourier Transform touches many things). _NCCL does not support the complex number out-of-the-box_. 

It turned out that adding complex-number support was not the big issue. The complex number is simply the contiguous array of, says, `float64`. Unlike typical `float64`, one element of `complex128` number is then represented by two `float64`. Things get more complicate if we start to talk about the complex number arithmatic. Luckily, [NCCL semantics](https://docs.nvidia.com/deeplearning/nccl/user-guide/docs/api/types.html#c.ncclRedOp_t) only supports _element-wise_ `ncclSum`, `ncclProd`, `ncclMin`, `ncclMax`,  `ncclAvg`. Wrapping element-wise operations for complex number is straightforward.

The change to PyLops-MPI `_nccl.py` itself is minimal. We simply added the function below and this hides the complexity of buffer-size management from users.
```python
def _nccl_buf_size(buf, count=None):
    """ Get an appropriate buffer size according to the dtype of buf
    if buf.dtype in ['complex64', 'complex128']:
        return 2 * count if count else 2 * buf.size
    else:
        return count if count else buf.size
```
The conceptual is quite simple. But mechanically, to get it right in the general case required some extensive bug fixing, particularly in the call to `_allgather `as noted earlier in the "Core Change" section. The array needs some preprocessing (to align with NCCL semantics) and post-processing so that the result from Pylops-MPI’s NCCL allgather matches with the PyLops-MPI allgather. This is because Pylops-MPI must be able to switch between `mpi4py` and NCCL seamlessly from the user's perspective. To make it concrete, here is how we do the `_allgather()` with NCCL
```python
    def _allgather(self, send_buf, recv_buf=None):
        """Allgather operation
        """
        if deps.nccl_enabled and self.base_comm_nccl:
            if isinstance(send_buf, (tuple, list, int)):
                return nccl_allgather(self.base_comm_nccl, send_buf, recv_buf)
            else:
                send_shapes = self.base_comm.allgather(send_buf.shape)
                (padded_send, padded_recv) = _prepare_nccl_allgather_inputs(send_buf, send_shapes)
                raw_recv = nccl_allgather(self.base_comm_nccl, padded_send, recv_buf if recv_buf else padded_recv)
                return _unroll_nccl_allgather_recv(raw_recv, padded_send.shape, send_shapes)
        # < snip - MPI allgather >
 ```

**After this feature was added, the PyLops-MPI with NCCL now catches up with its original MPI implementation, i.e., the test coverage is now the same 306 tests passed !**

- ### Benchmark Instrumentation [PR #157](https://github.com/PyLops/pylops-mpi/pull/157)
Profiling distributed GPU operations is critical to understanding performance bottlenecks. To make this easier, we added a _lightweight benchmark instrumentation_ framework in PyLops-MPI. The goal was to allow developers to mark execution points in a function and collect timing information for these markers.

The core of the implementation is a `@benchmark decorator`. Inside a decorated function, developers can call `mark(label)` to record the time at specific points. After the function completes, the timings are reported in a human-readable format. This design is inspired by C++-style instrumentation, letting developers place markers directly in the code where they are most informative. 

But because we are in Python, to handle nested function calls, we collect the timing information as a stack (bottom-up call graph) and parse the result at the end of the decorated function. Here's is the illustration:
```python
@benchmark
def outer_func_with_mark(par):
    mark("Outer func start")
    inner_func_with_mark(par) # <- this does `dot` and is also decorated
    dist_arr = DistributedArray(global_shape=par['global_shape'],
                                partition=par['partition'],
                                dtype=par['dtype'], axis=par['axis'])
    dist_arr + dist_arr
    mark("Outer func ends")
```
The text output is 
```
[decorator]outer_func_with_mark: total runtime: 0.001206 s
        [decorator]inner_func_with_mark: total runtime: 0.000351 s
                Begin array constructor-->Begin dot: 0.000026 s
                Begin dot-->Finish dot: 0.000322 s
        Outer func start-->Outer func ends: 0.001202 s
```

Benchmarking is controlled via the environment variable `BENCH_PYLOPS_MPI`. It defaults to `1` (enable) but can be set to `0` to skip benchmarking for clean output. **This means users can leave the decorated code unchanged and disable the benchmark through the environment variable**. This is inspired by the C++ debug flag set during the compilation. Moreover, careful attention had to be made on concurrency issue of benchmarking because the time is recorded by CPU while the NCCL issues the operation in an async manner to CUDA stream [PR #163](https://github.com/PyLops/pylops-mpi/pull/163) is an example of this.

- ### Benchmark Result
This was the moment of truth. Our 12-week hardwork would be judged by a set of hard cold numbers. Our expectation was that
  - If the system does not have proprietary NVLink for GPU-GPU communication but is NCCL-compatible, the communication using `CuPy + NCCL` should still be faster than `NumPy + MPI` (and possibly`CuPy + MPI`) in PyLops-MPI i.e., there should be a benefit from using NCCL from communication-related optimizations enabled by this project.

The result below was from NCSA UIUC Delta system [4-Way NVIDIA A40 GPU](https://docs.ncsa.illinois.edu/systems/delta/en/latest/user_guide/architecture.html) (no NVLink) with the `allreduce` operation.

<p align="center">
<img width="400" height="300" alt="image" src="https://gist.github.com/user-attachments/assets/b139e63d-11ed-47f4-95f8-5e86bed26312" />
</p>

That meets our expection. One thing to note here is: we see that actually the `CuPy + MPI` communication being slower than the `NumPy + MPI`. This is because the current implementation of PyLops-MPI uses non-buffered calls of `mpi4py` - see detail [here](https://mpi4py.readthedocs.io/en/stable/tutorial.html). The choice was made due to its simplicity as it allowed send and receiving generic Python object wrapped in a `list` and thus allowed fast development process. However, These require the memory copy from GPU to CPU, do communication, and copy memory from CPU to GPU (pickle protocol) - see our discussion with `mpi4py` community [here](https://github.com/mpi4py/mpi4py/discussions/657). This leads us to “Things left to do” section (later).

  - If the system has an NVLink for GPU-GPU communication, we will be able to see a significant gain in performance of PyLops-MPI with NCCL. 

The result below is also from NCSA UIUC Delta system [8-Way NVIDIA H200 GPU](https://docs.ncsa.illinois.edu/systems/delta/en/latest/user_guide/architecture.html) (with NVLink) but we only use 4 GPUs to compare with previous result. This is also with the `allreduce` operation.

<p align="center">
<img width="400" height="300" alt="image" src="https://gist.github.com/user-attachments/assets/b3d83547-b9af-4b1c-87c0-ace2302eb140" />
</p>

Here we unleash the true power of NCCL and its infrasture as you can see that **the bandwidth of PyLops-MPI with NCCL is 800x of the MPI implementation !**. It may not make much sense to compare the number with `NumPy+MPI` because there is drastic hardware infrastructure upgrade involved.

To top things off, we also ran the experiment trying to saturate the communication with the array size going up to 32 GB in total. We can see that we have the linear scaling i.e. time vs. data size grows linearly.
<p align="center">
<img width="400" height="300" alt="image" src="https://gist.github.com/user-attachments/assets/e5a95fdc-8db7-4caf-925f-256f504603bc" />
</p>

Finally, we ran an experiment with the application of [Least-squares Migration](https://wiki.seg.org/wiki/Least-squares_migration), which is an iterative inversion scheme:
  - Each iteration applies a forward  `A` and an adjoint `A.T` operation to form residuals and gradients.
  - A gradient accumulation  requires a global reduction across processes with `allreduce`.
Note that the computation is not trivial and so the total run-time of CPU and GPU is not fairly comparable (notice that in H200, the CuPy+MPI is not the slowest anymore). But we want to give the idea of how things piece together in the real application.
<div align="center">
  <img width="400" height="300" alt="kirchA40" 
       src="https://gist.github.com/user-attachments/assets/46c3a76a-20a3-40c3-981e-6e1c4acecb49" />
  <img width="400" height="300" alt="kirchhoff_h200" 
       src="https://gist.github.com/user-attachments/assets/1439304a-8f78-4640-a78b-ba37238b26e6" />
</div>


### The impact of this GSoC project is clear:
With our NCCL-enabled PyLops-MPI,
  - if you don't have access to the state-of-the-art infrastructure, PyLops-MPI with NCCL can still 10x the communication bandwith (A40 case)
  - if you do, we allow you to get the most out of the system (H200 case).

And the best thing is to use NCCL with PyLops-MPI, it requires minimal code change as shown in this [LSM Tutorial](https://github.com/PyLops/pylops-mpi/blob/main/tutorials_nccl/lsm_nccl.py) and illustrated below. Only two change require from the code that run on MPI: the array must be allocated in GPU and nccl has to be passed to the `DistributedArray`. And that's it !

```python
nccl_comm = pylops_mpi.utils._nccl.initialize_nccl_comm()

# <snip - same set-up as running with MPI>

lsm = LSM(
    # <snip>
    cp.asarray(wav.astype(np.float32)), # Copy to GPU
    # <snip>
    engine="cuda",
    dtype=np.float32
)
lsm.Demop.trav_srcs = cp.asarray(lsm.Demop.trav_srcs.astype(np.float32))  # Copy to GPU
lsm.Demop.trav_recs = cp.asarray(lsm.Demop.trav_recs.astype(np.float32))  # Copy to GPU

x0 = pylops_mpi.DistributedArray(VStack.shape[1],
                                 partition=pylops_mpi.Partition.BROADCAST,
                                 base_comm_nccl=nccl_comm, # Explicitly pass nccl communicator
                                 engine="cupy") # Must use CuPy
# <snip - the rest is the same>
```

### Things left to do
  - CUDA-Aware MPI: As we pointed out in the A40 experiment that current implementation of PyLops-MPI use non-buffered calls of `mpi4py` and thus introduces the memory copying from GPU to CPU. We aim to optimize this by introducing the buffered calls. However, this is not a trivial task because some of the MPI-related code was developed based on the semantics that the communication return the `list` object while the buffered call will return the array instead.