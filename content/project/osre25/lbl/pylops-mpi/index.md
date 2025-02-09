---
title: "Towards High Performance NCCL-enabled 2D partitioned PyLops-MPI library"
authors: [yuxihong, matteoravasi, nanding]
author_notes: ["Postdoc Researcher, Lawrence Berkeley Lab","Senior Research Advisor, Shearwater GeoServices", "Research Scientist, Lawrence Berkeley Lab"]
tags: ["osre25", "Seismic Redatuming", "PyLops", "Distributed Algorithms"]
date: 2025-02-09T10:15:56-07:00
lastmod: 2025-02-09T10:15:56-07:00
---

###  Project Description
<!--- PyLops and PyLops-MPI introduction --->
<!--- importance --->
[PyLops](https://github.com/PyLops/pyLops) ecosystem designed to enable large-scale, distributed-memory computations for matrix-free inverse problems. PyLops has achieved more than 400 stars till now. [PyLops-MPI](https://github.com/PyLops/pyLops-mpi) is an extension of the PyLops. It can be widely used in scientific computation problems, especially in the computational geophysics. Developed as part of the [2023 Google Summer of Code](https://summerofcode.withgoogle.com/archive/2023/projects/eNJTJO25), PyLops-MPI builds on the core PyLops framework by integrating MPI-based parallelism through the mpi4py library. This allows users to efficiently scale PyLops-based computations beyond a single node, leveraging high-performance computing (HPC) clusters for tackling increasingly large problem sizes.

By extending PyLops' modular and user-friendly interface to distributed environments, PyLops-MPI provides researchers and engineers with a powerful tool for developing scalable scientific applications across disciplines, from geophysics to machine learning. As part of the broader PyLops ecosystem, it represents a significant step toward high-performance, parallel inverse problem solving, catering to both academia and industry. 

This project is designed based on the roadmap of PyLops-MPI library. We plan to provide three major functionalities for the PyLops-MPI. Firstly, in the PyLops-MPI library, we support the NVIDIA GPU where we operates data on GPU. However, when we communciate, we need to copy data back to CPU and call mpi4py. We plan to use NCCL instead of mpi4py when we call GPU routines. Secondly, the parallelism of PyLops-MPI is achieved through spliting the computation of different frequency matrices to different MPI processors. It might not be scalable when we have multiply right hand side inverse problems. We propose to support standard 2D SUMMA algorithm for the computation. The frequency matrices will be split in 2D blocks and this will improve the scalability of the library. Finally, we would like to benchmark MPI one-sided API in PyLops-MPI library since asynchronous execution features of one-sided API will improve the scalability of the algorithm. 

### Project Objectives
<!--- Our goal 2D parallisem, NCCL, one-sided MPI --->
Aligned with the vision of the 2025 Open Source Research Experience (OSRE), the project aims to benchmark and extend the capability of the PyLops-MPI library in the distributed environment. Below is an outline of the algorithms to be developed in this project: 


- **Goal 1: Enabling NCCL API in PyLops-MPI Library**: Understanding the design of PyLops-MPI. Using NCCL API for collective communication in PyLops-MPI when data is on GPU. Benchmarking the performance of NCCL compared with mpi4py in different scenarios. 

- **Goal 2: Benchmarking 2D Parallelism in PyLops-MPI Library**: Understanding the design of PyLops-MPI. Understanding the design of 2D partition design in current PyLops-MPI library. Benchmarking the performance of 2D partition design in PyLops-MPI compared with original 1D partition design.

- **Goal 3: Enabling MPI One-sided API in PyLops-MPI Library**: Understanding the design of PyLops-MPI. Uderstanding the message roofline model and MPI one-sided API. Implementing the one-sided communication strategies in the PyLops-MPI library.


### Project Deliverables
The PyLops-MPI is hosted in github at [Repo](https://github.com/PyLops/pyLops-mpi). [The paper](https://joss.theoj.org/papers/10.21105/joss.07512) mainly describes the design of the PyLops-MPI. Our mentors are the main developers and deisgner of the PyLops-MPI. Our mentors are also experts in HPC and MPI libraries. We will select the proper the mentees for the projects and provide the benchmark results and new functionalities of PyLops-MPI by the end of the projects.
We plan to have two or three mentees for the projects since each goal is a milestone for PyLops-MPI. The three goals can be achieved seperately, they are orthogonal to each other and can be exectuted in parallel. 

### PyLops-MPI

- **Topics**: Towards High Performance NCCL-enabled 2D partitioned PyLops-MPI library
- **Skills**: Proficient in Python, Experience with MPI, Experience with GPU
- **Difficulty**: Medium
- **Size**: Medium (200 hours)
- **Mentor**: {{% mention yuxihong %}}, matteoravasi, nanding



