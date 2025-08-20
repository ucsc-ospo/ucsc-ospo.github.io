---
title: "[Final]Reproducibility of Interactive Notebooks in Distributed Environments"
subtitle: ""
summary:
authors: 
  - rahmad
tags: ["osre25"]
categories: [distribute systems, notebooks]
date: 2025-08-20
lastmod: 2025-08-20
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

I am sharing a overview of my project [Reproducibility of Interactive Notebooks in Distributed Environments](/report/osre25/ucsc/06122025-rahmad) and the work that I did this summer.

# Project Overview
This project aims at improving the reproducibility of interactive notebooks which are executed in a distributed environment. Notebooks like in the [Jupyter](https://jupyter.org/) environment have become increasingly popular and are widely used in the scientific community due to their ease of use and portability. Reproducing these notebooks is a challenging task especially in a distributed cluster environment.

In the distributed environments we consider, the notebook code is divided into manager and worker code. The manager code is the main entry point of the program which divides the task at hand into one or more worker codes which run in a parallel, distributed fashion. We utlize several open source tools to package and containerize the application code which can be used to reproduce it across different machines and environments. They include [Sciunit](https://github.com/radiant-systems-lab/sciunit), [FLINC](https://github.com/radiant-systems-lab/Flinc), and [TaskVine](https://cctools.readthedocs.io/en/stable/taskvine/). These are the high-level goals of this project:
1. Generate execution logs for a notebook program.
2. Generate code and data dependencies for notebook programs in an automated manner.
3. Utilize the generated dependencies at various granularities to automate the deployment and execution of notebooks in a parallel and distributed environment.
4. Audit and package the notebook code running in a distributed environment.
5. Overall, support efficient reproducibility of programs in a notebook program.

# Progress Highlights
Here are the details of the work that I did during this summer.
## Generation of Execution Logs
We generate execution logs for the notebook programs in a distributed environment the Linux utility [strace](https://man7.org/linux/man-pages/man1/strace.1.html) which records every system call made by the notebook. It includes all files accessed during its execution. We collect separate logs for both manager and the worker code since they are executed on different machines and the dependencies for both are different. By recording the entire notebook execution, we capture all libraries, packages, and data files referenced during notebook execution in the form of execution logs. These logs are then utilized for further analyses.

## Extracting Software Dependencies
When a library such as a Python package like *Numpy* is used by the notebook program, an entry is made in the execution log which has  the complete path of the accessed library file(s) along with additional information. We analyze the execution logs for both manager and workers to find and enlist all dependencies. So far, we are limited to Python packages, though this methodology is general and can be used to find dependencies for any programing langauge. For Python packages, their version numbers are also obtained by querying the pacakge managers like *pip* or *Conda* on the local system.

## Extracting Data Dependencies
We utilze similar execution logs to identify which data files were used by the notebook program. The list of logged files also contain various configuration or setting files used by certain packages and libraries. These files are removed from the list of data dependencies through post-processing done by analyzing file paths. 

## Testing the Pipeline
We have conducted our experiments on three use cases obtained from different domains using between 5 and 10 workers. They include distributed image convolution, climate trend analysis, and high energy physics experiment analysis. The results so far are promising with good accuracy and with a slight running time overhead.

For this level of fine-grained analysis, 

## Processing at Cell-level
We perform the same steps of log generation and data and software dependency extraction at the level of individual cells in a notebook instead of once for the whole notebook. As a result, we generate software and data dependencies at the level of individual notebook cells. This is achieved by interrupting control flow before and after execution of each cell to write special instructions to the execution log for marking boundaries of cell execution. We then analyze the intervals between these instructions to identify which files and Python packages are accessed by each specific cell. We use this information to generate the list of software dependencies used by that cell only.

We also capture data dependencies by overriding analyzing the execution logs generated by overriding the function of the *open* function call used to access various files.

## Distributed Notebook Auditing
In order to execute and audit workloads in parallel, we use [Sciunit Parallel](https://github.com/radiant-systems-lab/parallel-sciunit) which uses GNU Parallel for efficient parallel execution of tasks. The user specifies the number of tasks or machines to run the task on which is then distributed across them. Once the execution completes, their containerized executions need to be gathered at the host location.

## Efficient Reproducibility with Checkpointing
An important challenge with Jupyter notebooks is that sometimes they are unnecessarily time-consuming and resource-intensive, especially when most cells remain unchanged. We worked on [NBRewind](https://github.com/talha129/NBRewind/tree/master) which is a lightweight tool to accelerate notebook re-execution by avoiding redundant computation. It integrates checkpointing, application virtualization, and content-based deduplication. It enables two kinds of checkpoints: incremental and full-state. In incremental checkpoints, notebook states and dependencies across multiple cells are stored once such that only their deltas are stored again. In full-state checkpoints, the same is stored after each cell. During its restore process, it restores outputs for unchanged cells and thus enables efficient re-execution. Our empirical
evaluation demonstrates that NBRewind can significantly reduce both  notebook audit and repeat times with incremental checkpoints.

I am very happy abut the experience I have had in this project and I would encourage other students to join this program in the future.