---
title: "Exploration of I/O Reproducibility with HDF5"
authors: [kakulo,wei]
author_notes: ["Computer Scientist, Pacific Northwest National Laboratory", "Postdoctoral Researcher, Lawrence Berkeley National Laboratory"]
tags: ["reproducibility", "uc", "osre25", "I/O", "storage", "PNNL", "LBL"]
date: 2025-02-19T09:00:00-07:00
lastmod: 2025-02-20T09:00:00-07:00
---

Parallel I/O is a critical component in high-performance computing (HPC), allowing multiple processes to read and write data concurrently from a shared storage system. [HDF5](https://github.com/HDFGroup/hdf5)—a widely adopted data model and library for managing complex scientific data—supports parallel I/O but introduces challenges in I/O reproducibility, where repeated executions do not always produce identical results. This lack of reproducibility can stem from non-deterministic execution orders, variations in collective buffering strategies, and race conditions in metadata and dataset chunking operations within HDF5’s parallel I/O hierarchy. Moreover, many HDF5 operations that leverage [MPI I/O]((https://www.hdfgroup.org/wp-content/uploads/2020/02/20200206_ECPTutorial-final.pdf)) require collective communication; that is, all processes within a communicator must participate in operations such as metadata creation, chunk allocation, and data aggregation. These collective calls ensure that the file structure and data layout remain consistent across processes, but they also introduce additional synchronization complexity that can impact reproducibility if not properly managed. In HPC scientific workflows, consistent I/O reproducibility is essential for accurate debugging, validation, and benchmarking, ensuring that scientific results are both verifiable and trustworthy. Tools such as [h5bench](https://github.com/hpc-io/h5bench)—a suite of I/O kernels designed to exercise HDF5 I/O on parallel file systems—play an important role in identifying these reproducibility challenges, tuning performance, and ultimately supporting the overall robustness of large-scale scientific applications.

### Workplan

The proposed work will include (1) analyzing and characterizing parallel I/O operations in [HDF5](https://www.hdfgroup.org/wp-content/uploads/2020/02/20200206_ECPTutorial-final.pdf) with [h5bench](https://github.com/hpc-io/h5bench) miniapps, (2) exploring and validating potential reproducibility challenges within the parallel I/O hierarchy (e.g., MPI I/O), and (3) implementing solutions to address parallel I/O reproducibility. 

- **Topics:** `Parallel I/O` `MPI-I/O` `Reproducibility` `HPC` `HDF5`
- **Skills:** C/C++, Python
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** {{% mention kakulo %}} and [Wei Zhang]{{% mention wei %}}
