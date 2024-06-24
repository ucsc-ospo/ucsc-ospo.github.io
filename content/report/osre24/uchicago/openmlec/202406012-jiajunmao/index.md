---
title: "OpenMLEC: Open-source MLEC implementation with HDFS on top of ZFS"
subtitle: ""
summary: ""
authors:
 - jiajunmao
 - mengwanguc
 - anjus-george
tags: ["osre24", reproducibility, "storage system", "distributed system"]
categories: []
date: 2024-06-12
lastmod: 2024-06-12
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

Hello, I'm {{%mention jiajunmao%}}, a BS/MS student at the University of Chicago studying Computer Science. I will be spending this summer working on the project [OpenMLEC: Open-source MLEC implementation with HDFS on top of ZFS](https://ucsc-ospo.github.io/project/osre24/ornl/openmlec/) under the mentorship of {{% mention mengwanguc %}}
and {{% mention anjus-george %}}, my [proposal](https://docs.google.com/document/d/1nYgNlGdl0jUgW8avpu671oRpMoxaZHZPwlDfBNXRVro/edit?usp=sharing).

How to increase data’s durability and reliability while decreasing storage cost have always been interesting topics of research. Erasure coded storage systems in recent years have been seen as strong candidates to replace replications for colder storage tiers. In the paper “Design Considerations and Analysis of Multi-Level Erasure Coding in Large-Scale Data Centers”, the authors explored using theory and simulation on how a multiple tiered erasure coded system can out-perform systems using single level erasure codes in areas such as encoding throughput and network bandwidth consumed for repair, addressing a few pain points in adopting erasure coded storage systems. I will be implementing the theoretical and simulation result of this paper by building on top of HDFS and ZFS, and benchmarking the system performance.

The project will aim to achieve
- HDFS understanding the underlying characteristics of ZFS as the filesystem
- HDFS understanding the failure report from ZFS, and use new and special MLEC repair logic to execute parity repair
- ZFS will be able to accept repair data from HDFS to repair a suspended pool caused by catastrophic data corruption




