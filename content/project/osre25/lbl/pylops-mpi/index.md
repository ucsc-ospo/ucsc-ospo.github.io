---
title: "Towards High Performance NCCL-enabled 2D partitioned PyLops-MPI library"
authors: [yuxihong, matteoravasi, nanding]
author_notes: ["Postdoc Researcher, Lawrence Berkeley Lab","Senior Research Advisor, Shearwater GeoServices", "Research Scientist, Lawrence Berkeley Lab"]
tags: ["osre25", "PyLops-MPI", "Distributed Algorithms"]
date: 2025-02-09T10:15:56-07:00
lastmod: 2025-02-09T10:15:56-07:00
---

###  Project Description
<!--- PyLops and PyLops-MPI introduction --->
<!--- importance --->
[PyLops](https://github.com/PyLops/pyLops) ecosystem designed to enable large-scale, distributed-memory computations for matrix-free inverse problems. PyLops has achieved more than 400 stars till now. [PyLops-MPI](https://github.com/PyLops/pyLops-mpi) is an extension of the PyLops. It can be widely used in scientific computation problems. Developed as part of the [2023 Google Summer of Code](https://summerofcode.withgoogle.com/archive/2023/projects/eNJTJO25), PyLops-MPI builds on the core PyLops framework by integrating MPI-based parallelism through the mpi4py library. This allows users to efficiently scale PyLops-based computations beyond a single node, leveraging high-performance computing (HPC) clusters for tackling increasingly large problem sizes.

By extending PyLops' modular and user-friendly interface to distributed environments, PyLops-MPI provides researchers and engineers with a powerful tool for developing scalable scientific applications across disciplines, from geophysics to machine learning. As part of the broader PyLops ecosystem, it represents a significant step toward high-performance, parallel inverse problem solving, catering to both academia and industry. 

PyLops-MPI is aimed to provide an efficient and user-friendly distibuted inverse problem solution. The software are designed to handle all three distinct use-cases in the distributed inverse problem: (1) Both model and data are fully distributed across nodes. (2) Data are distributed across nodes but model is available at all nodes. (3) Both model and data are available in all nodes (or just in the master). There are multiple use-cases for PyLops-MPI, e.g. [Least-squares Migration](https://pylops.github.io/pylops-mpi/tutorials/lsm.html#sphx-glr-tutorials-lsm-py), [Multi-Dimensional Deconvolution](https://pylops.github.io/pylops-mpi/tutorials/mdd.html#sphx-glr-tutorials-mdd-py) and [Post Stack Inversion - 3D](https://pylops.github.io/pylops-mpi/tutorials/poststack.html#sphx-glr-tutorials-poststack-py). We've already provided a solution based on mpi4py. With the development of PyLops-MPI, we plan to upgrade the communication infrastructure of PyLops-MPI to better support GPU-based cluster and reduce the overall datavement. This will further boost the performance of PyLops-MPI. 

This project is designed based on the roadmap of PyLops-MPI library. We plan to provide three major functionalities for the PyLops-MPI. Firstly, in the PyLops-MPI library, we support the NVIDIA GPU where we operates data on GPU. We are relying on [CUDA-Aware MPI implementaiton](https://mpi4py.readthedocs.io/en/stable/tutorial.html#gpu-aware-mpi-python-gpu-arrays) in mpi4py. It requires a CUDA-Aware MPI software stacks which is strict to the system software. Alternatively, we can use NCCL instead of mpi4py when we call GPU routines. NCCL also has better support for NVLink etc. Secondly, the parallelism of PyLops-MPI is achieved through spliting the data and models to different MPI processors. It might not be scalable when we have multiply right hand side inverse problems. We have a [2D partitioned implementation](https://github.com/PyLops/pylops-mpi/issues/113) while we don't know exactly the performance of the implementation. Thus, we propose to benchmark the scalability of the new 2D partitioned implementation. We are aware that other distibuted matrix-matrix multiplication algorithms such as 2D SUMMA algorithm can be incoporated into the PyLops-MPI library. We would also like to implement the 2D SUMMA algorithm if time permits. Finally, we would like to benchmark MPI one-sided API in PyLops-MPI library since asynchronous execution features of one-sided API will improve the scalability of the algorithm. 

### Project Objectives
<!--- Our goal 2D parallisem, NCCL, one-sided MPI --->
Aligned with the vision of the 2025 Open Source Research Experience (OSRE), the project aims to benchmark and extend the capability of the PyLops-MPI library in the distributed environment. Below is an outline of the algorithms to be developed in this project: 


- **Goal 1: Enabling NCCL API in PyLops-MPI Library**: Understanding the design of PyLops-MPI. Using NCCL API for collective communication in PyLops-MPI when data is on GPU. Benchmarking the performance of NCCL compared with mpi4py in different scenarios. 

- **Goal 2: Benchmarking 2D Parallelism in PyLops-MPI Library**: Understanding the design of PyLops-MPI. Understanding the design of 2D partition design in current PyLops-MPI library. Benchmarking the performance of 2D partition design in PyLops-MPI compared with original 1D partition design. If possible, implement the 2D SUMMA algorithm. 

- **Goal 3: Enabling MPI One-sided API in PyLops-MPI Library**: Understanding the design of PyLops-MPI. Uderstanding the message roofline model and MPI one-sided API. Implementing the one-sided communication strategies in the PyLops-MPI library.

### Project Benchmark Suites
We plan to use at least three use cases in the [tutorial sections](https://pylops.github.io/pylops-mpi/tutorials/) in PyLops-MPI. We will measure the communication volume and time to solution of these use-cases.

### Project Benchmark Testbeds
Yuxi Hong is granted access to the world-leading supercomputers such as Delta, Delta-AI through an [ACCESS funded grant](https://www.xras.org/public/requests/193551-ACCESS-CIS250038). [Delta](https://docs.ncsa.illinois.edu/systems/delta/en/latest/) is a dedicated, ACCESS-allocated resource designed by HPE and NCSA, delivering a highly capable GPU-focused compute environment for GPU and CPU workloads. [DeltaAI](https://docs.ncsa.illinois.edu/systems/deltaai/en/latest/) is a companion system to Delta. Powered by the NVIDIA GH200 Grace Hopper Superchip, DeltaAI provides powerful compute capabilities for simulation and data science. The team also has access to [Perlmutter](https://docs.nersc.gov/systems/perlmutter/architecture/) supercomputer based in LBNL. 


### Project Deliverables
The PyLops-MPI is hosted in github at [Repo](https://github.com/PyLops/pyLops-mpi). [The paper](https://joss.theoj.org/papers/10.21105/joss.07512) mainly describes the design of the PyLops-MPI. Our mentors are the main developers and deisgner of the PyLops-MPI. Our mentors are also experts in HPC and MPI libraries. We will select the proper the mentees for the projects and provide the benchmark results and new functionalities of PyLops-MPI by the end of the projects.
We plan to have two or three mentees for the projects since each goal is a milestone for PyLops-MPI. The three goals can be achieved seperately, they are orthogonal to each other and can be exectuted in parallel. 

### PyLops-MPI

- **Topics**: Towards High Performance NCCL-enabled 2D partitioned PyLops-MPI library
- **Skills**: Proficient in Python, Experience with MPI, Experience with GPU
- **Difficulty**: Medium
- **Size**: Medium (200 hours)
- **Mentor**: {{% mention yuxihong %}}, matteoravasi, nanding



