---
title: Reproducible Performance Benchmark for Genomics Workflows on HPC Cluster
authors: [inkee.kim]
author_notes: ["Assistant Professor of School of Computing, University of Georgia"]
tags: [osre24, reproducibility, genomics, High Performance Computing (HPC), Performance Modeling, Data Analysis, Scientific Workflows]
date: 2024-02-02
lastmod: 2024-02-02
---

**Project Idea description**

A thorough understanding of workload is a crucial component in designing novel and high-performing scheduling systems. In the context of genomics workflow, the workload often consists of large input files (e.g., tens to hundreds of GB per file) that are processed by a diverse set of applications. Each application has its own resource utilization characteristics, ranging from I/O bound, memory-bound, compute-bound, up to a combination of them. Thus, it is crucial to accurately measure and document these characteristics in order to build a high-performance scheduler.

Such measurement effort is commonly done using benchmarking tools. However, many existing benchmarks for genomics applications are neither comprehensive nor scalable. Many benchmarks only support a subset of the resources that we need to measure (e.g., only compute and memory, but not I/O). Moreover, we found no benchmarks designed for many concurrent and multi-node executions, even though it is the common setup for production systems. The capability is important because the systems community has long known that a complex system often exhibits unexpected behavior at scale. Benchmarking tools that do not support scalable execution risk providing inaccurate measurement when compared to production systems.

In this project, we aim to build a comprehensive and scalable benchmarking tool for genomics workflows on a HPC cluster. Students will be able to learn genomics data processing using state-of-art applications and workflows using real-world data. They will also build and package a resource monitoring system for I/O, memory, and compute utilization using industry-grade tools and best practices. Following that, students will analyze the resource utilization of various applications and create performance models under different resource allocation and colocation degrees. Along the way, students can produce an open-source dataset, which, given sufficient quality, we plan to release to the public. All experiments will be done in a reproducible manner (e.g., as a Trovi package or Chameleon VM image), and all code will be made open-source (e.g., shared on a public Github repo).

**Project Deliverable**

A Github repository and/or Chameleon VM image containing source code for application executions & resource monitoring systems.
Jupyter notebooks and/or Trovi artifacts containing analysis & mathematical models of application resource utilization. 


- **Topics:** High Performance Computing (HPC), Performance Modeling, Data Analysis, Scientific Workflows
- **Skills:** Linux, Python, Bash Scripting, Cloud Computing, Data Science Toolkit (e.g. Numpy, Pandas, SciPy)
- **Difficulty:** Medium
- **Size:** 350 hours
- **Mentor(s):** Inkee Kim
