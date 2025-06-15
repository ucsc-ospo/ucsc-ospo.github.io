---
title: "Optimizing and Benchmarking GPU Collective Communication of PyLops-MPI with NCCL"
subtitle: "GPU-to-GPU Communication in PyLops-MPI for Large-scale Inverse Problems with Nvidia's NCCL" 
summary:
authors: 
  - tharitt 
tags: ["gsoc25","lbl","PyLops-MPI"]
categories: ["High-performance Computing", "GPU", "NCCL", "Parallel Programming"]
date: 2025-06-08
lastmod: 2025-06-08
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

# Google Summer of Code ‘25: Optimizing and Benchmarking GPU Collective Communication of PyLops-MPI with NCCL

My project aims to introduce GPU-to-GPU collective communication calls using Nvidia's NCCL to [PyLops-MPI](https://github.com/PyLops/pylops-mpi), an extension of the powerful [PyLops](https://github.com/PyLops/pylops) library.

I'm incredibly grateful for this opportunity and excited to be mentored by two HPC experts, Yuxi Hong from Lawrence Berkeley National Laboratory and Matteo Ravasi from ShearWater GeoServices.

Here's also the link to my original [proposal](https://summerofcode.withgoogle.com/programs/2025/projects/C2XSZp2E) 

## What is PyLops-MPI and NCCL ?

 PyLops is a Python library that provides a rich collection of linear operators to solve inverse problems. Its MPI extension, PyLops-MPI, takes this a step further by enabling these operations to run on large-scale, distributed computing systems like HPC using the Message-Passing Interface (MPI).

Where does NCCL fit in? The NVIDIA Collective Communication Library (NCCL) is a library of highly-optimized routines for collective communication between GPU. It offers the opportunity to close the performance gap in PyLops-MPI. As we now offload more and more computationally intensive tasks to GPUs, the communication between them can become a bottleneck. NCCL offers a powerful solution to this problem, enabling high-bandwidth, low-latency communication that can significantly boost performance.


## Motivation and What was Missing

As a student with a background in geophysics (B.Sc) and now pursuing computer science (M.Sc), I've experienced firsthand the challenges of scaling scientific computing research from a personal desktop to a high-performance computing (HPC) cluster. It can be a significant hurdle. My project aims to ease this transition for PyLops-MPI users. PyLops-MPI is something I wish existed while I was doing my undergraduate reseach !

Currently, PyLops-MPI is "CUDA-aware," meaning it can offload computations to GPUs. However, the communication between those GPUs is still handled by the underlying MPI implementation, which isn't always optimal. This project will address this gap by integrating NCCL to handle GPU-to-GPU communication directly. If the compute is done in GPU, there shouldn't be a copy from GPU to CPU, transfer with MPI, and put them back to GPU again.

This will be especially impactful for memory-bound problems where high-bandwidth communication is critical. By the end of this project, we'll have a clear, quantifiable understanding of the performance gains achieved.

## My Best-Laid Plan

My approach is grounded in good software engineering practices to ensure that this new feature is both robust and genuinely useful. I was impressed by the code quality (enjoyable read) of the repository - and so I commit not to break that.

First and foremost, the goal is to seamlessly integrate NCCL without breaking what already works. A significant part of my effort will be dedicated to rigorous testing. This means not only ensuring that all existing tests pass but also developing a new, comprehensive test suite to validate the correctness of the GPU-to-GPU communication across different hardware setups. 

Once we're confident that the integration is solid, the exciting part begins: benchmarking (or you may call it "Moment of Truth")! The plan is to measure the performance of end-to-end iterative solvers. These solvers are a perfect test case because they involve a mix of intensive gradient computations on the GPU and frequent AllReduce calls to sync up processes. This will give us a clear picture of the speedup and efficiency gains from using NCCL.

Finally, to make sure this work benefits the entire community, I will create clear documentation and tutorials. The goal is to make it easy for any user to leverage this new GPU-accelerated communication in their own research and applications.
