---
title: "Mid Term Blog: FetchPipe: Data Science Pipeline for ML-based Prefetching"
subtitle: ""
summary: ""
authors:
 - peiranqin
tags: ["osre24", reproducibility, "machine learning"]
categories: []
date: 2024-07-27
lastmod: 2024-07-27
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


## Introduction

Hello, I’m {{%mention peiranqin%}}, a CS student at the University of Chicago, currently working on the project [FetchPipe: Data Science Pipeline for ML-based Prefetching](/project/osre24/uchicago/fetchpipe/) under the mentorship of Prof. {{% mention haryadi%}}. The FetchPipe project focuses on building a unified python simulator and evaluating the existing chache-eviction and ML-Based prefetcher under this simulator. 

## Motivation

Existing prefetching algorithms can be categorized into (a) heuristic-based methods such as the Linux lookahead prefetcher and (b) machine learning-based methods like Long Short Term Memory (LSTM) models. However, there is a research gap in comprehensively comparing all existing ML solutions, such as Leap and LSTM Prefetcher, under a consistent evaluation setup. To ensure the fairness of evaluations, it is essential to integrate all baselines and our prefetcher into a homogeneous evaluation environment. Additionally, there is a need to evaluate cache eviction algorithms under prefetching scenarios.

Therefore, in this project, we aim to build a fair simulator, deploy state-of-the-art prefetchers and cache eviction algorithms onto this platform, and then evaluate them using comprehensive metrics. The state-of-the-art prefetchers we consider include Pythia (MICRO'21), SGDP (arXiv), and the Markov-Chain prefetcher. For cache eviction algorithms, we consider S3FIFO (SOSP'23) and SIEVE (NSDI'24). Our focus is on implementing these algorithms on our simulator and evaluating their performance using block storage datasets from Alibaba, Tencent, and MSR. Besides evaluating the prefetchers and eviction algorithms individually, we also aim to combine prefetchers with cache eviction algorithms to test overall performance.

## Current Progress

In the past one and a half months, I have focused on (1) implementing our Python simulator and (2) deploying state-of-the-art prefetchers and cache eviction algorithms on this simulator. The implementation phase is now complete. The detailed progress is as follows:  

1. The python simulator of evaluating both ML-based or heuristic-based prefetchers and cache eviction are done.  
2. Evaluations metrics collection, such as hit rate, total prefetched data, prefetch overhead, prefetch accuracy are implemented on the simulator.  
3. Two ML-based prefetchers, SGDP, Pythia and Markov-Chain are deployed on the simulator. SGDP is a graphed neural network based prefetcher, and Pythia is a reinforment learning based prefetcher.  
4. State-of-the-art heuristic based eviction algorithms are implemented in the simulator, including S3FIFO and SIEVE.  

With the simulator and state-of-the-art ML-based prefetchers and eviction algorithms in place, the next steps are to (1) organize a large-scale dataset (including over 600 traces from real storage servers) for testing performance and (2) evaluate the implemented prefetchers and eviction algorithms on this dataset. Finally, I will analyze the evaluation results and provide insights from the experimental outcomes. For the ML-based prefetchers, I will analyze both ML-related metrics such as accuracy and F1-score, and system metrics such as hit rate and various overheads.


## Challenges
The biggest challenge is implementing existing prefetchers correctly and fairly. Since some state-of-the-art prefetchers are designed for DRAM prefetching, adapting them for SSD prefetching in the simulator is challenging. Additionally, the lack of source code for some works makes it difficult to reproduce their algorithms accurately based solely on their paper descriptions.