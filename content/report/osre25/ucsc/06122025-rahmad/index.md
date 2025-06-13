---
title: "Reproducibility of Interactive Notebooks in Distributed Environments"
subtitle: ""
summary: "Improving reproducibility of interactive notebooks in large-scale, distributed environments"
authors: 
  - rahmad
  - tanu-malik
tags: ["osre25", "notebooks", "distributed systems"]
categories: ["open source", "distributed systems", "notebooks", "DePaul University"]
date: 2025-06-12
lastmod: 2025-06-13
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Reproducibility"
  focal_point: "Top"
  preview_only: false
---

Hello! I am Raza, currently a Ph.D. student in Computer Science at DePaul University. This summer, I will be working on reproducibility of notebooks in distributed enviornments, mentored by Prof. [Tanu Malik](https://ucsc-ospo.github.io/author/tanu-malik/). Here is a summary of my project proposal.

Interactive notebooks are web-based systems which enable encapsulating code, data, and their outputs for sharing and reproducibility. They have gained wide popularity in scientific computing due to their ease of use and portability. However, reproducing notebooks in different target environments remains challenging because notebooks do not carry the computational environment in which they are executed. This becomes even more challenging in distributed cluster environments where a notebook must be prepared to run on multiple nodes. In this project, we plan to (i) extend [FLINC](https://github.com/radiant-systems-lab/Flinc), an open-source user-space tool for distributed environments such that it can package notebook executions into notebook containers for execution and sharing across distributed environments, and (ii) integrate the extended Flinc with [TaskVine](https://cctools.readthedocs.io/en/stable/taskvine/), which provides the framework and orchestration to enable distributed notebook execution in high performance computing environments.

[You can read my complete proposal here.](https://docs.google.com/document/d/1ilm-yMEq-UTiJPGMl8tQc3Anl5cKM5RD2sUGInLjLbU)

I am excited to work on this project and learn from the experience here!