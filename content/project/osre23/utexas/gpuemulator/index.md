---
title: GPU Emulator for Easy Reproducibility of DNN Training
authors: [Vijay Chidambaram]
author_notes: ["Associate Professor, Department of Computer Science, The University of Texas at Austin"]
tags: [osre23, reproducibility, DNN, GPU, performance]
date: 2023-02-05
lastmod: 2023-02-05
---

Deep Neural Networks (DNN) have achieved success in many machine learning (ML) tasks including image recognition, video classification and natural language processing. Nonetheless, training DNN models is highly computation intensive and usually requires running complex computations on GPUs, while GPU is a very expensive and scarce resource. Therefore, many research works on DNN training are delayed because of the lack of access to GPUs. However, many research prototypes don't require GPUs but only the performance profiles of GPUs. For example, research on DNN training storage systems doesn’t need to run real computations on GPUs, but only needs to know how much time each GPU computation will take. Meanwhile, GPU performance in DNN training is predictable and reproducible, as every batch of training performs a deterministic sequence of mathematical operations on a fixed number of data.

Therefore, in this project we seek to build a GPU emulator platform on PyTorch to easily reproduce DNN training without using real GPUs. We will measure the performance profiles of GPU computations for different models, GPU types, and batch sizes. Based on the measured GPU performance profiles, we will build a platform to emulate the GPU behaviors and reproduce DNN training using CPUs only. We will make the platform and the measurements open-source, allowing other researchers to reproduce the performance measurements and easily conduct research on DNN training systems. We will also encourage the community to enrich the database by adding GPU performance measurements for their own models and GPU types. We will be the first one to build and release this kind of GPU emulator for DNN training, and we believe researchers and the community can benefit a lot from it, especially after more and more GPU performance profiles are added by the community.

### Building a platform to emulate GPU performance in DNN training
- **Topics:** DNN training, reproducibility, GPU emulator, performance measurement - Skills: Linux, Python, PyTorch, deep learning
- **Difficulty:** Medium
- **Size:** 350 hours
- **Mentor(s):** [Vijay Chidambaram](mailto:vijayc@utexas.edu), [Yeonju Ro](mailto:yro@utexas.edu)

The student will measure the GPU performance profiles for different models and GPU types, based on which the student will build a platform to emulate the GPU behaviors and easily reproduce DNN training. The GPU performance measurements should be made open-source and reproducible for other researchers to reproduce results and add GPU profiles for their own needs.

Specific tasks:
- Work with mentors on understanding the context of the project.
- Study and get familiar with the PyTorch DNN training pipelines
- Measure GPU performance profiles for different DNN models and GPU types
- Based on the GPU performance measurements, build a platform to emulate the GPU behaviors and reproduce DNN training without using real GPUs
- Organize and document the codes to make them reproducible for the community
