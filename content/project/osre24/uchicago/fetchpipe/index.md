---
title: "FetchPipe: Data Science Pipeline for ML-based Prefetching " 
authors: [haryadi, daniar]
author_notes: [Associate Professor at the University of Chicago, PhD Cand. at the University of Chicago]
tags: [osre24, reproducibility, "storage systems", machine learning"]
date: 2024-02-02
lastmod: 2024-02-06
---

**Project Idea Description**

- **Topics:** Storage systems, machine learning
- **Skills:** C/C++, Python, PyTorch, Bash scripting, Linux, Machine Learning modeling 
- **Difficulty:** Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention daniar %}} (primary contact), Haryadi Gunawi


The contemporary landscape of high-performance servers, particularly those designed for data centers and AI/ML training, prominently features solid-state drives (SSDs) and spinning disks (HDDs) as primary storage devices. These components play a crucial role in shaping overall system performance, underscoring the importance of addressing and minimizing Input/Output (I/O) latency. This is particularly crucial given the widespread adoption of hybrid storage systems, where caching and prefetching strategies are instrumental in optimizing storage performance. Caching involves using faster but less dense memory to store frequently accessed data, while prefetching aims to reduce latency by fetching data from slower memory to cache before it is needed. Although both caching and prefetching present valid challenges, our primary emphasis is on the prefetching problem due to the inherent difficulty in predicting future access. 

Traditional prefetchers, dating back 1-2 decades, heavily rely on predefined rules for prefetching based on LBA access sequences, limiting their adaptability to complex scenarios. For instance, the read-ahead prefetcher is confined to prefetching the next data item within a file for faster sequential access. Addressing this limitation, recent advancements include learning-based methods, such as Long Short-Term Memory (LSTM) techniques like DeepPrefetcher and Delta LSTM, which model the LBA delta to cover a broader range of LBAs. However, they are still struggling to achieve high accuracy when the workload pattern changes drastically. Although there are some sophisticated prefetchers capable of learning complex I/O access patterns using Graph structure, they face challenges in their deployment due to the computational cost. 

In this project, our goal is to provide an end-to-end data science pipeline to empower the research on ML-based prefetchers. We believe that this pipeline is crucial for fostering active collaboration between the ML community and storage systems researchers. This collaboration aims to optimize existing ML-based prefetching solutions. Specifically, we will provide the dataset for training/testing and some samples of ML-based models that can further be developed by the community. Furthermore, we will also provide a setup for evaluating the ML model when deployed in storage systems. 

**Project Deliverable**
- Compile I/O traces from various open traces and open systems.
- Develop a pipeline for building ML-based prefetching solutions.
- Build a setup to evaluate the model in a real hybrid storage system.
- Publish a Trovi artifact shared on Chameleon Cloud and a GitHub repository

