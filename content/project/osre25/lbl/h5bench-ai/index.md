---
title: "h5bench with AI workloads"
authors: [jeanlucabez, surenbyna]
author_notes: ["Research Scientist, Lawrence Berkeley Lab", " The Ohio State University (OSU)"]
tags: ["osre25", "uc", "LBNL", "data science", "benchmarking", "AI"]
date: 2025-02-11T10:15:00-07:00
lastmod: 2025-02-11T10:15:00-07:00
---

[h5bench](https://github.com/hpc-io/h5bench) is a suite of parallel I/O benchmarks or kernels representing I/O patterns that are commonly used in HDF5 applications on high performance computing systems. h5bench measures I/O performance from various aspects, including the I/O overhead, and observed I/O rate. 

Parallel I/O is a critical technique for moving data between compute and storage subsystems of supercomputers. With massive amounts of data produced or consumed by compute nodes, high-performant parallel I/O is essential. I/O benchmarks play an important role in this process; however, there is a scarcity of I/O benchmarks representative of current workloads on HPC systems. Toward creating representative I/O kernels from real-world applications, we have created h5bench, a set of I/O kernels that exercise HDF5 I/O on parallel file systems in numerous dimensions. Our focus on HDF5 is due to the parallel I/O library's heavy usage in various scientific applications running on supercomputing systems. The various tests benchmarked in the h5bench suite include I/O operations (read and write), data locality (arrays of basic data types and arrays of structures), array dimensionality (1D arrays, 2D meshes, 3D cubes), I/O modes (synchronous and asynchronous). h5bench measurements can be used to identify performance bottlenecks and their root causes and evaluate I/O optimizations. As the I/O patterns of h5bench are diverse and capture the I/O behaviors of various HPC applications, this study will be helpful to the broader supercomputing and I/O community.

### h5bench with AI workloads

The proposed work will include (1) analyzing and characterizing AI workloads that rely on HDF5 datasets, (2) extracting a kernel of their I/O operations, and (3) implementing and validating the kernel in h5bench. 

- **Topics:** `I/O` `HPC` `benchmarking`
- **Skills:** Python, C/C++, good communicator
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** {{% mention jeanlucabez %}} and {{% mention surenbyna %}}