---
title: "Final Blog: FetchPipe: Data Science Pipeline for ML-based Prefetching"
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


Hello, I’m {{%mention peiranqin%}}, a CS student at the University of Chicago. This summer I worked on the project [FetchPipe: Data Science Pipeline for ML-based Prefetching](/project/osre24/uchicago/fetchpipe/) under the mentorship of Prof. {{% mention haryadi%}}. The FetchPipe project focuses on building a unified Python simulator and evaluating the existing cache-eviction policy and ML-based prefetcher under this simulator. Through this projects, we make the following contributions and get several insights that can share with the community:  


1. We built up a simulator to evaluate various prefetchers under a unified framework, under the production level traces from Alibaba, Microsoft Research, and Tencent.  
2. Through the evaluation, we discover several downsides that existing heuristic-based prefetchers encounter.  
3. We draw several insights that can guide the future prefetchers' design.  


## Methodology  
In the first half of the SoR project, I mainly focus on the **simulator building of I/O prefetcher**. The simulator should mimic the real OS-level prefetching as much as possible. First, we develop a mechanism that mimics the users sending I/O requests to the underlying systems. Then, we simulate the process of page division, and memory management inside the systems. Finally, we designed a sleep-based mechanism to mimic the I/O latency of backend storage. The outcome system can eventually simulate the data path of I/O request and prefetching of real systems, and collect the crucial metrics such as hit rate, total prefetched data, bandwidth usage, prefetch accuracy, total cache eviction, etc.  


In the second half of the SoR project, I concentrate on the **evaluation of existing prefetchers**. First, we surveyed the existing state-of-the-art prefetchers and divided them into two categories: (1) Heuristic-based prefetchers and (2) ML-based prefetchers. Next, for each category, we picked several representative prefetchers and implemented them within our simulator. Then, we evaluated those prefetchers using the production-level over 600 traces from Alibaba, Tencent, and Microsoft Research. Finally, we analyzed the performance of those prefetchers and discovered some interesting insights that might guide the future prefeters's design.  


Finally, based on the achievements of the SoR project, I will continue involving this interesting project with Prof. {{% mention haryadi%}}. We are leveraging the current insights we get to build an I/O prefetcher that mitigates the downsides of existing prefetchers.  




## Insights  
Based on our experiments on the existing prefetchers, we would like the share the following insights:
1. Heuristic-based prefetchers, including Linux Readahead and Stride prefetcher, rely on strict pre-fined rules and detect straightforward access patterns. However, those prefetchers are too conservative to recognize the increasingly complex access patterns. Especially, in real-world applications, sequential accesses are interweaved with random accesses, leading to a next-level complexity that makes it difficult for Linux Readahead and Stride prefetchers to recognize.  


2. Offline learning-based prefetchers learn the access patterns by training machine learning models on pre-collected historical access patterns. Blessed by the representational power of machine learning, these prefetchers excel at recognizing complex access patterns. However, their effectiveness is constrained by their dependence on the patterns encountered during offline training, making them less adaptable to previously unseen patterns in online scenarios. Moreover, due to not relying on the pre-defined rule of prefetching, Offline learning-based prefetchers are more prone to prefetch useless data, which causes cache pollution and extra pressure on backend storage.  


3. We argue that a good prefetcher under nowadays complex and changing workload should have three properties: (1) Complexity-Recognition: which means the prefetcher should be able to recognize the complex access pattern of a complex workload. (2) Reliability: means the prefetcher should reduce its possibility to prefetch using less data and cause cache pollution. (3) Adaptability: means the prefetcher should adapt itself to the changing workload.  


## Future Works  


Based on the above insights, we are now designing our own prefetchers that can mitigate the downsides of existing prefetchers. We will make our code public after we finalize our design.  


## Conclusion  
Through the SoR project, I delved into the research area of I/O prefetching by reproducing the related works, characterizing their performance, and designing our own prefetcher. We contribute to the community with a comprehensive simulator, evaluation results of related prefetchers, and insights that can guide the future prefetchers' design. In the future, I will continue working on the research area of prefetcher and keep making contributions.
