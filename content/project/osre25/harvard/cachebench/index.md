---
title: "CacheBench: Building a Benchmarking Suite for Cache Performance Evaluation"
authors: [juncheng]
author_notes: [Assistant Professor, Harvard University]
tags: [osre25, reproducibility]
date: 2025-02-28
lastmod: 2025-03-02
---

### Overview
In this project, we aim to develop a comprehensive benchmarking suite, CacheBench, for evaluating the performance of cache systems in modern computing environments. Caches play a crucial role in enhancing system performance by reducing latency and improving data access speeds. However, evaluating cache performance is a complex task that requires a diverse set of workloads and metrics to capture the cache's behavior accurately. The current focus is on the eviction algorithms and if time permits, we will extend to other components of cache design. 

This project will have three main components:
1. Implementing and benchmarking existing cache eviction algorithms in [libCacheSim](https://libcachesim.com/) using large-scale simulation. This part will mainly focus on reproducing existing works. 
2. Developing a set of microbenchmarks and a platform for researchers to evaluate new designs with little effort in the future. This part will focus on building the open-source infrastructure for future research. 
3. Developing a leaderboard for the community to submit new algorithms and workloads. This part will focus on building the community and fostering adoption and collaboration. 


- **Topics:** storage systems, benchmarking, performance evaluation
- **Skills:** C programming, web programming (e.g., node.js, React), database management
- **Difficulty:** Moderate
- **Size:** Large (350 hours). 
- **Mentors:** {{% mention juncheng %}}, Yazhuo Zhang (yazhuo@inf.ethz.ch)
