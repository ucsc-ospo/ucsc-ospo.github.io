---
title: "YOUR TITLE"
subtitle: "YOUR SUBTITLE (OPTIONAL)"
summary:
authors: 
  - USERNAME1
  - USERNAME2
tags: ["osre25"]
categories: []
date: YYYY-MM-DD
lastmod: YYYY-MM-DD
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

I am sharing a overview of my project [Reproducibility of Interactive Notebooks in Distributed Environments](/report/osre25/ucsc/06122025-rahmad) and an udpate at the midway mark. 

# Project Overview
This project aims at improving the reproducibility of interactive notebooks which are executed in a distributed environment. Notebooks like in the [Jupyter](https://jupyter.org/) environment have become increasingly popular and are widely used in the scientific community due to their ease of use and portability. Reproducing these notebooks is a challenging task especially in a distributed cluster environment.

In the distributed environments we consider, the notebook code is divided into manager and worker code. The manager code is the main entry point of the program which divides the task at hand into one or more worker codes which run in a parallel, distributed fashion. We utlize several open source tools to package and containerize the application code which can be used to reproduce it across different machines and environments. They include [Sciunit](https://github.com/radiant-systems-lab/sciunit), [FLINC](https://github.com/radiant-systems-lab/Flinc), and [TaskVine](https://cctools.readthedocs.io/en/stable/taskvine/). These are the high-level goals of this project:
1. Generate execution logs for a notebook program.
2. Generate code and data dependencies for notebook programs in an automated manner.
3. Utilize the generated dependencies at various granularities to automate the deployment and execution of notebooks in a parallel and distributed environment.
4. Audit and pacakge the notebook code running in a distributed environment.

# Progress So Far
Here are the details of the progress made so far.
## Generation of Execution Logs
We generate execution logs for the notebook programs in a distributed environment the Linux utility [strace](https://man7.org/linux/man-pages/man1/strace.1.html) which records every system call made by the notebook. It includes all files accessed during its execution. We collect separate logs for both manager and the worker code since they are executed on different machines and the dependencies for both are different. By recording the entire notebook execution, we capture all libraries, packages, and data files referenced during notebook execution in the form of execution logs. These logs are then utilized for further analyses.

## Extracting Software Dependencies
When a library such as a Python package like *Numpy* is used by the notebook program, an entry is made in the execution log which has  the complete path of the accessed library file(s) along with additional information. We analyze the execution logs for both manager and workers to find and enlist all dependencies. So far, we are limited to Python packages, though this methodology is general and can be used to find dependencies for any programing langauge. For Python packages, their version numbers are also obtained by querying the pacakge managers like *pip* or *Conda* on the local system.

## Extracting Data Dependencies
We utilze similar execution logs to identify which data files were used by the notebook program. The list of logged files also contain various configuration or setting files used by certain packages and libraries. These files are removed from the list of data dependencies through post-processing done by analyzing file paths. 

## Testing the Pipeline
We have conducted our experiments on three use cases obtained from different domains using between 5 and 10 workers. They include distributed image convolution, climate trend analysis, and high energy physics experiment analysis. The results so far are promising with good accuracy and with a slight running time overhead.

# Next Steps
The next steps in this project are as follows:
1. Generate the execution logs and dependencies in a notebook at the level of each cell of code. 
2. Utilize the dependencies at multiple levels of granularities with the goal of automating the deployment and execution of notebooks in a parallel and distributed environment.
3. Audit notebook program execution in a distributed environment and package it into a container on a single node.

I am very happy abut the experience I have had so far in this project and I am excited about the milestones to come.
Stay tuned!