---
title: Reproducible Evaluation of Multi-level Erasure Coding
authors: 
- john.bent
- Anjus George
author_notes: 
- "Senior Director, Seagate Technology"
- "HPC Storage R&D staff, Oak Ridge National Laboratory"
tags: ["osre23", "reproducibility", "storage systems", "erasure coding"]
date: 2023-02-02
lastmod: 2023-02-02
---

Massive storage systems rely heavily on erasure coding (EC) to protect data from drive failures and provide data durability. Existing storage systems mostly adopt single-level erasure coding (SLEC) to protect data, either performing EC at the network level or performing EC at the local level. However, both SLEC approaches have limitations, as network-only SLEC introduces heavy network traffic overhead, and local-only SLEC cannot tolerate rack failures. 

Accordingly, some data centers are starting to use multi-level erasure coding (MLEC), which is a hybrid approach performing EC at both the network level and the local level. However, prior EC research and evaluations mostly focused on SLEC, and it remains to be answered how MLEC is compared to SLEC in terms of durability, capacity overhead, encoding throughput, network traffic, and other overheads.

Therefore, in this project we seek to build a platform to evaluate the durability and overheads of MLEC. The platform will allow us to evaluate dozens of EC strategies in many dimensions including recovery strategies, chunk placement choices, various parity schemes, etc. To the best of our knowledge, there is no other evaluation platform like what we propose here. We seek to make the platform open-source and the evaluation reproducible, allowing future researchers to benefit from it and conduct more research on MLEC.

### Building a platform to evaluate MLEC
- **Topics:** Storage systems, reproducibility, erasure coding, evaluation
- **Skills:** Linux, C, Python
- **Difficulty:** Medium
- **Size:** 350 hours
- **Mentor(s):** {{% mention john.bent %}} and [Anjus George](mailto:georgea@ornl.gov)


Build a platform to evaluate the durability and overheads of MLEC. The platform will be able to evaluate different EC strategies in various dimensions including repair strategies, chunk placement choices, parity schemes, etc. Analyze the evaluation results.

Specific tasks:
- Work with mentors on understanding the context of the project.
- Reproduce the SLEC evaluation results from prior SLEC evaluation tools
- Based on prior SLEC evaluation tools, build a platform to evaluate the durability and overheads of MLEC under various EC strategies
- Collect and analyze the MLEC evaluation results

