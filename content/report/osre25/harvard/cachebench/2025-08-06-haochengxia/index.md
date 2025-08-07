---
title: "Midterm Report: Simulation, Comparison, and Conclusion of Cache Eviction"
subtitle: ""
summary: "Develop a comprehensive benchmarking suite, CacheBench, for evaluating the performance of cache systems in modern computing environments."
authors:
  - haochengxia
tags: ["osre25","reproducibility","storage systems"]
categories: ["SummerofReproducibility24"]
date: 2025-08-06
lastmod: 2025-08-06
featured: true
draft: false

image:
  caption: "Haocheng Xia, SoR 2025"
  focal_point: "Center"
  preview_only: false
---

## Project Overview

**CacheBench** is a benchmarking suite designed for comprehensive cache performance evaluation, with a particular focus on analyzing the miss ratios of various cache eviction algorithms.

At the core of CacheBench lie two key components: the high-performance cache simulator, [libCacheSim](https://github.com/1a1a11a/libCacheSim), and the extensive [open-source cache datasets](https://github.com/cacheMon/cache_dataset), which collectively contain over 8,000 traces from diverse applications. This ensures broad coverage across a range of realistic workloads.

Our primary goal is to evaluate all major and widely-used cache eviction algorithms on thousands of traces, in order to gain insights into their behaviors and design trade-offs. Additionally, we aim to identify and distill representative workloads, making benchmarking more efficient and comprehensive for future cache research.

## Progress and Pain Points

We began by benchmarking prevalent eviction algorithms, including FIFO, LRU, CLOCK, LFU, Random, Belady (BeladySize), CAR, ARC, LIRS, LHD, Hyperbolic, GDSF, W-TinyLFU, 2Q, SLRU, S3-FIFO, SIEVE, and LeCaR. As we developed the suite, we made progressive improvements to both the simulator and dataset infrastructure. Our progress can be summarized as follows:

- Collected miss ratio results for all listed algorithms across 8,000+ traces.
- Identified best- and worst-performing traces for each algorithm, and conducted feature analysis of these traces.
- Developed Python bindings: To increase accessibility, we provided a Python package that allows users to easily download traces and run simulation analyses using [libCacheSim](https://github.com/1a1a11a/libCacheSim) and the [cache datasets](https://github.com/cacheMon/cache_dataset).

However, analysis remains challenging because there is no universally accepted metric or baseline for objectively comparing cache eviction algorithms' performance across all workloads.

## Next Steps

For the second half of the project, my focus will shift to:

- **Evaluating More Complex Eviction Algorithms**: Having concentrated mainly on static eviction policies so far (which are generally more deterministic and understandable), I will now investigate learning-based eviction algorithms such as LRB and 3L-Cache. These models incorporate learning components and incur additional computational overhead, making simulations slower and more complex.

- **Detailed Trace Analysis**: Since eviction algorithms can have highly variable performance on the same trace, I plan to analyze why certain algorithms excel on specific traces while others do not. Understanding these factors is crucial to characterizing both the algorithms and the workload traces.

- **Constructing Representative Workload Sets**: Based on ongoing simulations and trace analyses, I aim to identify a minimal but representative subset of traces that can serve as a basic evaluation suite, simplifying testing and improving accessibility.

## Reflection

This project has truly been the highlight of my summer. By evaluating a wide range of cache eviction algorithms, I've significantly deepened my understanding of cache design and its underlying principles.

I'm especially grateful to my mentors for their constant support, patience, and guidance throughout this journey. It’s been a privilege to learn from you!

I'm excited to see the final results of CacheBench!