---
title: "OCEAN: Improving the infrastructure to enable memory hierarchy
optimizations"
subtitle:
summary: "This is a midterm update about the status of my project to improve
OCEAN's infrastructure to enable hierarchical memory tiering studies"
authors:
  - aldsmith
  - kakulo
tags: ["osre26", "pnnl", "CXL emulation", "Memory Systems"]
categories: []
date: 2026-08-16
lastmod: 2026-08-16
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "Smart"
  preview_only: false
---

Wow, how time flies! It's been two months since [introducing my
project](https://ucsc-ospo.github.io/report/osre26/ucmerced/cxl_emu/) for
OSRE'26! In my initial post, I highlighted the need for simulator
infrastructure to enable memory hierarchy studies and I set out to do this by
firstly improving the infrastructure of OCEAN. I did this primarily by
improving the statistics OCEAN collects during simulation, adding CI/CD
tests to ensure correctness, and allowing kernels/images to be brought up by
users.


## Progress

### Dumping OCEAN's Statistics

Since starting the GSoC project, OCEAN was missing functionality to add stat de-
scriptors to a file and log the values at some given interval for bookkeeping. The CXLMemSim src provided in the repo actually has some functionality to log, but this is done roughly every 100k operations and does not capture the output to any file. I have improved upon this by adding a knob to tune how frequently stats get changed. If 1there is no interval, then there is just one cumulative dump at the end of the file. The outputs are logged to a server.log file by default.

### Building an image and kernel from scratch

Setting up OCEAN takes significant effort, as you have to run several setup
scripts and obtain fairly large kernel and image files. While you can
certainly download the the kernel and disk images, per [OCEAN's
README](https://github.com/fam-emu/OCEAN/blob/main/README.md), there are users
who would like to compile their own images and kernels. Using a fork of the
[Linux kernel](https://github.com/vickiegpt/linux-cxl-type2) the packer
script takes this, compiles it, and produces a `bzImage` artifact, which is
used by OCEAN's launch scripts. This is not yet public, but will be pushed by
the end of the summer!


### CI/CD Pipeline

One of the main things that OCEAN lacks is validating the disk and kernel
images are set up correctly. To ensure this is the case, I've implemented
CI/CD tests which do the following:

1. `./script/setup_host.sh` is ran and ensures that any prerequisites (e.g.,
packages, successful compilation of QEMU) are completed before running any
experiments
2. `./script/setup_network.sh` is ran and ensure `n` number of VMs are
supported and IP interfaces are available for the VMs.
3. `qemu.img` and `bzImage` are downloaded. Using the launch scripts,
`qemu.img` is booted and configured so SSH access is enabled to transfer
necessary programs. `qemu.img` is also duplicated to `qemu1.img and this copy
has its' hostname changed so mutli-host programs using CXL memory run to
completion.
4. The CXLMemSim server is booted up with a 1GB CXL interface (i.e.,
`./cxlmemsim_server --capacity 1024`) alongside one two QEMU VMs the disk
images we created.
5. When the VMs boot up, we inspect available devices and ensure that
`/dev/dax0.0` appears. `/dev/dax0.0` is the CXL device that the VMs see and
allows them to communicate with CXLMemSim.
6. Given that the VMs properly support CXL, an MPI workload (GROMACS) is
launched to ensure communication works between two VMs.

Most of this has been largely validated to work; however given that OCEAN's
companion paper is slated to appear in Supercomputing 2026, it is worth coming
back to these CI/CD tests and re-running similar experiments to the figures
within the paper. Additionally, the kernel and disk image reconstruction
mentioned above is not a part of the CI/CD tests and will be implemented
before the end of summer.

### Interleaving and Evaluation Studies

As mentioned, the tooling improvements will enable CXL interleaving studies to
reduce the effects of the memory bottelneck. One potential approach to do this
is to consider what if we placed CXL at different levels of the memory
heirarchy (e.g., what if CXL acts as a cache or DRAM?). In this case, we might
want to change caching strategies to improve performance (e.g., what kind of
cache-line granularity is the best for each level? what data should we evict
or prefetch?). While the initial proposal suggested going right into QEMU
there, I am opting to use a systems-level library (libPGAS) and sketching an
initial memory model to test this scheme. My approach to implement this has
multiple steps:

* We need to consider the types of structures we'd want in a memory model (coherence, prefetching, cache-line granularity, coalescing, write policies)
* Once we implement the model, we need to make unit tests to evaluate the
 behavior of the model (i.e., does coherence behave the way we expect? if we
 implement a replacement policy like [LRU](https://www.geeksforgeeks.org/system-design/lru-cache-implementation/), is it correct?
* Once the behavior is reasonable, how can we implement this into libPGAS, QEMU, and CXLMemSim?

Right now, I am at a very rough stage implementing the caching model and I
have yet to touch many of the aspects described (e.g., prefetching policy).
Towrads the end of the summer, I plan to evaluate this model; and, if time
remains, implement this to the QEMU fork OCEAN uses.

## Remaining Tasks

To summarize the above, there's a couple of tasks that need to be done:

* Evaluating Tiering Memory Model: As described, I need to flesh out the model
and create/run unit tests to validate behavior
* Intercepting Requests with QEMU/OCEAN: Once the model has been validated, I
 need to port over the behavior. While it is unlikely I will get this working
in QEMU/OCEAN in time to survey the model under real workloads, as it requires
heavy work, this is much more feasible than looking into the KVM counters from
my initial proposal
* Finalize fixes and CI/CD tests: While most of the "infrastructure" is done,
 there are some pending fixes that will be completed before the end of the
 summer.

That's all for now! Stay tuned for the final report where I'll go through my
final results and publish a repo which contains my findings/outcomes for the
summer!
