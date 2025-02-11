---
title: "SciStream-Rep: An Artifact for Reproducible Benchmarks of Scientific Streaming Applications"
tags: [osre24, reproducibility]
authors: [chungmiranda, fcastro]
author_notes: ["Research Scientist at Argonne National Laboratory", "Systems Developer at Argonne National Laboratory"]
date: 2024-02-26
lastmod: 2024-02-26
---
[SciStream](https://github.com/scistream/scistream-proto) is a framework and toolkit that attempts to tackle the problem of enabling high-speed(+100Gbps), memory-to-memory data streaming in scientific environments. This task is particularly challenging because data producers (e.g., data acquisition applications on scientific instruments, simulations on supercomputers) and consumers (e.g., data analysis applications) may be in different security domains and thus require bridging of those domains. Furthermore, either producers, consumers, or both may lack external network connectivity and thus require traffic forwarding proxies. If you want to learn more, please take a look at our [HPDC'22 paper](https://dl.acm.org/doi/abs/10.1145/3502181.3531475).

### SciStream-Rep: An Artifact for Reproducible Benchmarks of Scientific Streaming Applications

**Project Idea Description:**

- **Topics**: Network Performance Testing, Benchmarking, Data Streaming, Reproducibility
- **Skills**: Python, Scripting, Linux, Containers, Networking, benchmark tools
- **Difficulty**: Medium
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

This project focuses on expanding the scope of testing SciStream’s architecture by incorporating a variety of traffic patterns based on real scientific applications. The goal is to understand how different traffic patterns influence the performance of memory-to-memory data streaming in scientific scenarios by creating artifacts for reproducible experiments. Additionally, the project will explore the use of different forwarding elements, such as Nginx and HAProxy, to assess their impact on data streaming efficiency and security. 

Reproducibility is especially difficult in shared network environments such as Chameleon and FABRIC testbeds. We can expect similar results for two exact same experiments, only when the network condition (external to our traffic) is similar for both experiments. By creating reproducible artifacts for Chameleon and FABRIC, we can build statistical confidence in the measured results by multiple repetitions from other researchers.

The Specific Tasks of the Project Include:

- Developing a set of benchmarks to measure the performance of scientific streaming applications across a broader range of traffic patterns.
- Creating a set of artifacts for generating traffic patterns typical of data streaming applications.
- Deploying various forwarding elements within the SciStream architecture for the Chameleon and FABRIC testbeds.
- Compiling a best practices document detailing the optimal configurations for Scistream.

### Scistream-LB: A Dynamic Load Balancing Solution Using Programmable network devices

**Project Idea Description:**
- **Topics**: Network Performance Testing, Data Streaming, Reproducibility, Programmable Data Planes
- **Skills**: Python/Scripting, Linux, Docker/Containers, Networking fundamentals, Experience with OpenFlow/P4 programming
- **Difficulty**: Difficult
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

The aim of this project is to create a specialized forwarding element using OpenFlow (OF) or P4 programming languages, tailored to enhance the SciStream data plane. This new development seeks to enable a more flexible and hardware-based (and therefore more efficient) alternative to conventional software-based forwarding mechanisms like NGINX or HAProxy, specifically designed to support the needs of high-performance data streaming environments for scientific applications. The OF/P4 forwarding elements will be packaged as artifacts for reproducibility experiments in Chameleon and FABRIC testbeds. Reproducibility is especially difficult in shared network environments such as Chameleon and FABRIC testbeds. We can expect similar results for two exact same experiments, only when the network condition (external to our traffic) is similar for both experiments. By creating reproducible artifacts for Chameleon and FABRIC, we can build statistical confidence in the measured results by multiple repetitions from other researchers.

Specific tasks of the project include:
- Design and implementation of an OF/P4-based forwarding element that can be seamlessly integrated with the data plane of SciStream’s architecture.
- Forwarding logic that supports efficient and secure memory-to-memory data streaming.
- A set of benchmarks for evaluating the new forwarding element against traditional options, focusing on improvements in throughput, latency, and security.
- An investigation on the potential advantages of programmable network elements for detailed control over data streaming paths and security configurations.
- A package of the newly developed forwarding elements as artifacts for reproducibility experiments in Chameleon and FABRIC testbeds.
