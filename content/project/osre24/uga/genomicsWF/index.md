---
title: Reproducible Performance Benchmarking for Genomics Workflows on HPC Cluster
authors: [inkee.kim]
author_notes: ["Assistant Professor of School of Computing, University of Georgia"]
tags: [osre24, reproducibility, genomics, High Performance Computing (HPC), Performance Modeling, Data Analysis, Scientific Workflows]
date: 2024-02-02
lastmod: 2024-02-05
---

**Project Idea description**

A thorough understanding of workload is a crucial component in designing high-throughput systems. In the context of genomics workflow, the workloads are often composed of large input files (e.g., tens to hundreds of GB per file) that are processed by a diverse set of applications. Each application has its own resource utilization characteristics, ranging from I/O bound, memory-bound, and compute-bound, up to a combination of them. It is crucial to accurately measure and document these characteristics in order to leverage them for a particular target system.

Such measurement effort is commonly conducted through benchmarking. However, many existing studies for benchmarking genomics workflows tend to be either non-comprehensive or outdated, especially given the rapid innovation in the bioinformatics field. Often, these studies measure only a subset of the resources that are needed (e.g., only compute and memory, but not I/O). Moreover, we found there are surprisingly few such studies in the last years, despite various software/hardware advancements that have been made.

We aim to bridge this gap in understanding genomic workflows by conducting a comprehensive characterization of a broad set of genomics applications. Students will have the opportunity to learn genomics data processing using state-of-the-art applications, workflows, and real-world data. They will collect and package datasets for I/O, memory, and compute utilization using industry-standard tools and best practices. Students will also explore to investigate the correlation of input data size/quality to application execution time. Subsequently, they will analyze the dataset and create a performance model for each application. We will make the generated dataset & analysis publicly accessible, given adequate quality. All experiments will also be conducted in a reproducible manner (e.g., as a Trovi package or Chameleon VM images), and all code will be open-sourced (e.g., shared on a public Github repo).


**Project Deliverable**

A Github repository and/or Chameleon VM image containing source code for application executions & metrics collection.
Jupyter notebooks and/or Trovi artifacts containing analysis and mathematical models for application resource utilization & the effects of data quality. 


- **Topics:** High Performance Computing (HPC), Performance Modeling, Data Analysis, Scientific Workflows
- **Skills:** Linux, Python, Bash Scripting, Cloud Computing, Machine Learning, Data Science Toolkit (e.g. Numpy, Pandas, SciPy)
- **Difficulty:** Difficult
- **Size:** Large (350 + 175) hours
- **Mentor(s):**  {{% mention inkee.kim %}}
