---
title: "Final Blog: SS_Bench - Benchmarking SciStream"
subtitle: "SciStream Artifact on FABRIC Testbed"
summary: ""
authors: [kraislaik]
tags: ["osre24", reproducibility]
categories: []
date: 2025-01-31
lastmod: 2024-01-31
featured: false
draft: false

image:
caption: ""
focal_point: ""
preview_only: false
---

## Introduction

Hello! My name is Acheme, and I'm thrilled to have collaborated with my mentors [Joaquin Chung](https://github.com/ucsc-ospo/ucsc-ospo.github.io/blob/main/content/authors/chungmiranda/_index.md) and  [Flavio Castro](https://github.com/ucsc-ospo/ucsc-ospo.github.io/blob/main/content/authors/fcastro/_index.md) under the [SciStream](/project/osre24/anl/scistream/) project. This project aims to develop SciStream-bench, a set of benchmarks and artifacts designed to precisely evaluate the performance of scientific streaming applications across diverse traffic patterns when running over the SciStream framework.

In the first half of the project, I focused on describing scientific streaming profiles based on use-cases experienced at Argonne National Lab. The necessary python scripts were developed to generate bursty and constant rate streaming traffic profiles.

In the second half, I built upon this foundation by conducting experiments with the traffic profiles and measuring performance through metrics of latency, jitter and throughput. These experiments were conducted with different message sizes across LAN and WAN network topology.

## Key Achievements

1. **Streaming Traffic Profile:**
   - Developed scripts to generate streaming traffic profiles with configurable parameters.

2. **Created an Artifact:**
   - I created an artifact using a Jupyter notebook to document an easy to follow integration of SciStream with FABRIC testbed for future experimenters.
 
## Conclusion and Future Work

The work demonstrated that SciStream offers tolerable overhead for secure data streaming and experimentation with this middlebox is possible in publicly available testbed like FABRIC.
Future work would be to look into the comparative analysis of the performance of SciStream with or without hardware acceleration or offloading.

## Deliverables

- **SciStream on FABRIC Demo:** A demo can be found here on how to integrate SciStream on the FABRIC testbed [SciStream on FABRIC](https://www.youtube.com/watch?v=2NNAWPAreU8).
- **Jupyter Notebook:** An Artifact on FABRIC portal: [FABRIC Artifact](https://artifacts.fabric-testbed.net/artifacts/1d604943-b5c0-4046-9971-ffb8f2535e42).
