---
title: "FlashNet: Towards Reproducible Data Science for Storage System" 
authors: [Haryadi Gunawi]
author_notes: [Associate Professor at the University of Chicago]
tags: [osre23, reproducibility, "storage systems", performance, "machine learning", “data science”]
date: 2023-02-02
lastmod: 2023-02-02
---

The Data Storage Research Vision 2025, organized in an NSF workshop, calls for more “AI for storage” research. However, performing ML-for-storage research can be a daunting task for new storage researchers. The person must know both the storage side as well the ML side as if studying two different fields at the same time. This project aims to answer these questions: 

1. How can we encourage data scientists to look into storage problems? 
2. How can we create a transparent platform that allows such decoupling? 
3. Within the storage/ML community can we create two collaborative communities, the storage engineers and the storage data scientists? 

In the ML/Deep Learning community, the large ImageNet benchmarks have spurred research in image recognition. Similarly, we would like to provide benchmarks for fostering storage research in ML-based per-IO latency prediction. Therefore, we present FlashNet, a reproducible data science platform for storage systems. To start a big task, we use I/O latency prediction as a case study. Thus, FlashNet has been built for I/O latency prediction tasks. With FlashNet, data engineers can collect the IO traces of various devices. The data scientists then can train the ML models to predict the IO latency based on those traces. All traces, results, and codes will be shared in the FlashNet training ground platform which utilizes Chameleon trovi for better reproducibility.

In this project, we plan to improve the modularity of the FlashNet pipeline and develop the Chameleon trovi packages. We will also continue to improve the performance of our binary-class and multiclass classifiers and test them on the new production traces that we collected from SNIA IOTA public trace repository. Finally, we will optimize the deployment of our continual-learning mechanism and test it in a cloud system environment. To the best of our knowledge, we are building the world-first end-to-end data science platform for storage systems. 

### Building FlashNet Platform

- **Topics:** Storage systems, reproducibility, machine learning, continual learning
- **Skills:** C++, Python, PyTorch, Experienced with Machine Learning pipeline
- **Difficulty:** Medium
- **Size:** 400 hours
- **Mentors:** [Haryadi Gunawi](https://people.cs.uchicago.edu/~haryadi/)

Build an open-source platform to enable collaboration between storage and ML communities, specifically to provide a common platform for advancing data science research for storage systems. The platform will be able to reproduce and evaluate different ML models/architecture, dataset patterns, data preprocessing techniques, and various feature engineering strategies. 

Specific tasks:
- Work with mentors on understanding the context of the project.
- Reproduce the FlashNet evaluation results from prior works.
- Build and improve FlashNet components based on the existing blueprint. 
- Collect and analyze the FlashNet evaluation results.
