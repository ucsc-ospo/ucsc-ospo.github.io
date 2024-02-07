---
title: "OpenMLEC: Open-source MLEC implementation with HDFS on top of ZFS" 
authors:
- georgea
- mengwanguc
author_notes:
- "HPC Storage R&D staff, Oak Ridge National Laboratory"
- "PhD Student, University of Chicago"
tags: ["osre24", "reproducibility", "storage systems", "erasure coding"]
date: 2024-02-05
lastmod: 2024-02-06
---

**Project Idea Description**

Multi-Level Erasure Coding (MLEC), which performs erasure coding at both network and local levels, has seen large deployments in practice. Our recent research work has shown that MLEC can provide high durability with higher encoding throughput and less repair network traffic compared to other erasure coding methods. This makes MLEC particularly appealing for large-scale data centers, especially high-performance computing (HPC) systems.

However, current MLEC systems often rely on straightforward design choices, such as Clustered/Clustered (C/C) chunk placement and the Repair-All (RALL) method for catastrophic local failures. Our recent simulations [1] have revealed the potential benefits of more complex chunk placement strategies like Clustered/Declustered (C/D), Declustered/Clustered (D/C), and Declustered/Declustered (D/D). Additionally, advanced repair methods such as Repair Failed Chunks Only (RFCO), Repair Hybrid (RHYB), and Repair Minimum (RMIN) have shown promise for improving durability and performance according to our simulations. Despite promising simulation results, these optimized design choices have not been implemented in real systems.

In this project, we propose to develop open-source MLEC implementations in real systems, offering a range of design choices from simple to complex. Our approach leverages ZFS for local-level erasure coding and HDFS for network-level erasure coding, supporting both clustered and declustered chunk placement at each level. The student's responsibilities include setting up HDFS on top of ZFS, configuring various MLEC chunk placements (e.g., C/D, D/C, D/D), and implementing advanced repair methods within HDFS and ZFS. The project will culminate in reproducible experiments to evaluate the performance of MLEC systems under different design choices.

We will open-source our code and aim to provide valuable insights to the community on optimizing erasure-coded systems. Additionally, we will provide comprehensive documentation of our work and share Trovi artifacts on Chameleon Cloud to facilitate easy reproducibility of our experiments.

[1] Meng Wang, Jiajun Mao, Rajdeep Rana, John Bent, Serkay Olmez, Anjus George, Garrett Wilson Ransom, Jun Li, and Haryadi S. Gunawi. Design Considerations and Analysis of Multi-Level Erasure Coding in Large- Scale Data Centers. In The International Conference for High Performance Computing, Networking, Storage and Analysis (SC ’23), 2023.


**Project Deliverable**
- Open-source MLEC implementations with a diverse range of design choices.
- Configuration setup for HDFS on top of ZFS, supporting various MLEC chunk placements.
- Implementation of advanced repair methods within HDFS and ZFS.
- Reproducible experiments to assess the performance of MLEC systems across distinct design choices.
- Comprehensive documentation of the project and the provision of shared Trovi artifacts on Chameleon Cloud for ease of reproducibility.


- **Topics:** Storage Systems, Erasure Coding
- **Skills:** C/C++, Java, Bash scripting, Linux, HDFS, ZFS, Erasure Coding
- **Difficulty:** Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention mengwanguc %}} ([Main contact person](mailto:wangm12@uchicago.edu)) and Anjus George

