---
title: "IO logger: IO tracing in the modern computing era"
authors: [juncheng]
author_notes: [Assistant Professor, Harvard University]
tags: [osre25, operating systems]
date: 2025-02-28
lastmod: 2025-03-02
---

### Overview
Storage systems are critical components of modern computing infrastructures, and understanding their performance characteristics is essential for optimizing system efficiency. There were many works from twenty to thirty years ago, but the landscape has changed significantly with the advent of 
* cloud computing, virtualization, and storage disaggregation on the **server side**
* ubiquitous fast wireless networking for **end users** that make remote storage feasible
* AI and ML workloads that generate and move massive data both in the cloud and on the edge.   

In this project, we aim to develop an IO logger, a tool for tracing, logging and analyzing IO operations in various computing environments. The IO logger will capture detailed information about read and write operations, latency, throughput, and other metrics to help researchers and practitioners understand the behavior of storage systems under different workloads and configurations. By providing a comprehensive view of IO performance, the IO logger will enable users to identify bottlenecks, optimize resource utilization, and improve system efficiency.


This project will have two phases: 
1. IO logger for *NIX systems: Develop a tool leveraging eBPF and other tools for tracing IO operations on Linux and other Unix-like systems. The tool will capture detailed information about disk reads and writes, network transfers, and other IO activities, providing insights into system performance. The tool will be open-sourced, and we will work with industry partners and testbeds to integrate it into existing monitoring and analysis tools. Moreover, we will collect and open source the IO traces to benefit the community. 
2. IO logger for personal computing environment: Develop a tool for end-users to trace IO operations on their personal devices, such as laptops, desktops, and mobile phones. We will design and implement tools for three different platforms, Window, MacOS and Andriod. We will use the tools to collect IO traces from volunteers and real-world applications. providing insights into storage usage, network activity, and application performance. The tool will be user-friendly, lightweight, and privacy-preserving, ensuring that users can monitor their IO activities without compromising their data security.  


Notable difference and challenges compared to the existing works are:
* **more IO requests with rich features**: open-source traces from previous works were collected all after page cache, which are often write-heavy, lose most IO requests, and do not provide enough features, e.g., process name. To address this, we will build a tool that can also records requests served by page cache, which requires the tool to be efficient and cannot impose significant overhead to the ruuning systems. 
* **focus on new applications and workloads**: the existing works were mostly outdated from the 1990s, during which the Internet has not been widely used, and applications are mostly processing local data and does not communicate with outside world. While there have been a few works looked into mobile storage a decade ago. The landscape has changed significantly since then, especially with the advent of AI and ML workloads that generate and move massive data both in the cloud and on the edge. This project will look into the difference and challenges brought by these new applications and workloads.


- **Topics:** tracing tool, operating system, eBPF, performance evaluation
- **Skills:** C programming, system programming, eBPF, Linux kernel, mobile application development
- **Difficulty:** Hard
- **Size:** Large (350 hours). 
- **Mentors:** {{% mention juncheng %}}


#### Related works
* [COSMOS] (https://dl.acm.org/doi/abs/10.1145/3460095)
* [mobile storage usage](https://dl.acm.org/doi/abs/10.1145/2987443.2987465)
* [mobile storage performance measurement](https://dl.acm.org/doi/abs/10.1145/2043106.2043112)
* [mobile application IO performance](https://ieeexplore.ieee.org/abstract/document/7897092)
* [stardust](https://dl.acm.org/doi/abs/10.1145/1140103.1140280)
* [GPFS](https://dl.acm.org/doi/abs/10.1145/3149376)





