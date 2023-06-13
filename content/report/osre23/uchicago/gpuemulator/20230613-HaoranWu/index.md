---
title: "GPU Emulator for Easy Reproducibility of DNN Training"
subtitle: ""
summary: ""
authors: [Haoran Wu]
author_notes: ["Student at the University of Chicago"]
tags: ["osre23"]
categories: [SoR'23]
date: 2023-06-13
lastmod: 2023-06-13
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

Hi! I’m Haoran Wu, a third year at the University of Chicago majoring in Economics and Computer Science. With my [proposal](https://docs.google.com/document/d/1CcNbvbNAmY0XkV9ckjHnILdMh92h1wqLUYqpT6qIsZY/edit?usp=sharing), I’m working on the [GPU Emulator for Easy Reproducibility of DNN Training](https://ospo.ucsc.edu/project/osre23/utexas/gpuemulator) project with [Professor Chidambaram](https://ospo.ucsc.edu/author/vijay-chidambaram). A Deep Neural Network (DNN) is an advanced artificial neural network that employs multiple layers to process intricate patterns and relationships within data. It finds applications in various fields such as image and speech recognition, natural language processing, and predictive modeling. The layers in a DNN progressively extract higher-level features from raw input data, enabling the network to learn and generalize patterns effectively.

The growing popularity of Deep Neural Networks has resulted in a substantial increase in demand for Graphics Processing Units (GPUs). GPUs are crucial for conducting matrix computations in DNN training and inference. However, they are expensive to purchase for personal use, and the limited availability of GPU resources in public research clouds like Chameleon further exacerbates the issue. This scarcity of resources can cause delays in DNN-related research projects.

Nevertheless, not all DNN research experiments require the use of a GPU. System researchers, for instance, may be primarily interested in performance profiles and not necessarily in the accuracy of training or inference. These researchers might focus on optimizing the storage layer and data loading of DNN training. In such cases, a GPU emulator that accurately replicates GPU behavior without needing a physical GPU can fulfill their requirements. By utilizing a GPU emulator, system researchers can evaluate their system optimizations' performance without competing for limited GPU resources in the cloud, thereby avoiding unnecessary delays in their research progress. Our work will eventually be open source and benefit the community. 