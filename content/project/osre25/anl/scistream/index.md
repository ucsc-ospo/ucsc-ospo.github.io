---
title: "Architecting the Future of Scientific Data: Multi-Site Streaming Without Compromise"
tags: [osre25, lanl, reproducibility, networking, data streaming, high performance computing, benchmarking, testbeds, cyber security]
authors: [chungmiranda, fcastro]
author_notes: ["Research Scientist at Argonne National Laboratory", "Systems Developer at Argonne National Laboratory"]
date: 2025-02-10
lastmod: 2025-02-12
---

Data is generated at ever-increasing rates, yet it’s often processed more slowly than it’s collected. Scientific instruments frequently operate below their full capacity or discard 
valuable data due to network bottlenecks, security domain mismatches, and insufficient real-time processing capabilities. 

[SciStream](https://github.com/scistream/scistream-proto) reimagines how scientific data moves across modern research infrastructure by providing a framework for high-speed (+100Gbps) 
memory-to-memory streaming that doesn’t compromise on security. Whether connecting scientific instruments to analysis clusters or bridging across institutional boundaries, SciStream provides the foundation for next-generation scientific 
workflows.

Building on our [published research](https://dl.acm.org/doi/abs/10.1145/3502181.3531475), we’re now expanding the framework’s capabilities through open-source development and community 
collaboration. These projects offer an opportunity for 
students to gain hands-on experience with cutting-edge networking and security technologies used in high-performance computing (HPC), cloud infrastructure, and large-scale scientific 
experiments.

### SciStream-SecureBench: A Framework for Benchmarking Security Protocols in Scientific Data Streaming

**Project Idea Description:**

- **Topics**: Security Protocols, Network Performance, Data Streaming, Reproducibility, High-throughput Computing
- **Skills**: Python, Scripting, Linux, Network Protocol Analysis, Containers, Benchmarking tools
- **Difficulty**: Medium
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

Ever wondered why large scientific experiments need to move massive amounts of data securely and quickly? While TLS and SSH are standard for secure data transfer, 
there’s a surprising lack of benchmarks that evaluate their performance in high-speed scientific workflows. This project aims to fill this gap by developing a benchmarking suite that 
measures how different security configurations impact real-time scientific data streaming.

### **Specific Tasks of the Project Include**

- Developing benchmarking tools that measure key security performance metrics like handshake latency, throughput stability, and computational overhead.
- Running **real-world experiments** on research testbeds (Chameleon, FABRIC) to simulate scientific data patterns.
- Automating comparative analysis between TLS and SSH, with focus on streaming-specific metrics like **time-to-first-byte and sustained throughput**.
- Documenting best practices for security protocol selection in high-performance streaming.

### **Why This Matters for Your Career**

- Gain expertise in **network security and performance analysis**, highly valued in cybersecurity, cloud computing, and HPC.
- Work on a **real research challenge** with potential for publication.

### SciStream-StreamBench: Comparative Analysis of Scientific Streaming Frameworks

**Project Idea Description:**

- **Topics**: Data Streaming Protocols, Network Performance, Benchmarking, Distributed Systems, Real-time Computing
- **Skills**: Python, ZeroMQ, EPICS/PVAccess, Linux, Performance Analysis, Visualization
- **Difficulty**: Medium
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

Scientific experiments generate enormous amounts of streaming data, but how do we choose the best framework for handling it efficiently? Despite the widespread use of ZeroMQ and 
[PVApy](https://dl.acm.org/doi/10.1145/3624062.3624610), 
there’s little systematic benchmarking comparing their performance. This project will develop **real-world benchmarks** to evaluate how different frameworks handle scientific data in 
**high-speed environments**.

### **The Specific Tasks of the Project Include**

- Designing benchmarking methodologies to assess key performance metrics like **synchronization overhead, time-to-first-data, and throughput stability**.
- Developing a test harness that simulates real-world streaming conditions (network variability, concurrent streams, dynamic data rates).
- Running experiments on **Chameleon and FABRIC testbeds**.
- Automating data collection and visualization to highlight performance trends.
- Documenting best practices and framework-specific optimizations.

### **Why This Matters for Your Career**

- Get hands-on experience with **real-time data processing** and **network performance analysis**.
- Learn benchmarking techniques useful for **distributed systems, cloud computing, and high-performance networking**.

### SciStream-QUIC: Next-Generation Proxy Architecture for Scientific Data Streaming

**Project Idea Description:**

- **Topics**: QUIC Protocol, Network Proxies, Performance Analysis, Protocol Design, Hardware Acceleration
- **Skills**: Python/C++, Network Programming, QUIC (quiche/aioquic), Linux, Performance Analysis
- **Difficulty**: Hard
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

Ever wondered how YouTube loads videos faster than traditional web pages? That’s because of **QUIC**, a next-generation protocol designed for speed and security. Initial evaluations 
of federated streaming architectures ([INDIS'22
paper](https://par.nsf.gov/servlets/purl/10380551)) suggest potential benefits of QUIC, but comprehensive benchmarking is
needed. This project explores whether **QUIC-based proxies** can outperform traditional **TCP+TLS** proxies for scientific data streaming, potentially revolutionizing how researchers move 
large datasets.

### **The Specific Tasks of the Project Include**

- Developing a **QUIC-based proxy** optimized for scientific workflows.
- Running benchmarks to compare **QUIC vs. traditional TLS proxies**.
- Investigating **hardware encryption offloading** for QUIC and TLS.
- Designing **reproducible experiments** using Chameleon and FABRIC testbeds.
- Documenting best practices for deploying **QUIC proxies in HPC environments**.

### **Why This Matters for Your Career**

- Gain experience in **cutting-edge networking protocols** used in cloud computing (Google, Cloudflare, etc.).
- Learn about **hardware acceleration** and its role in high-speed networking.

### SciStream-Auth: Modern Authentication and User Interface for Scientific Data Streaming

**Project Idea Description:**

- **Topics**: Authentication Systems, UI/UX Design, Security Integration, Scientific Computing
- **Skills**: Python, Web Development (React/Vue), OAuth 2.0/SAML, Security Analysis
- **Difficulty**: Medium
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

Not a security expert? You can still contribute by designing an interactive front-end!

In today's scientific computing landscape, authentication and user experience often act as barriers to adoption rather than enabling seamless collaboration. While SciStream excels at 
high-speed data transfer, its reliance on a single authentication provider and command-line interface limits its accessibility. This project aims to transform SciStream into a more 
versatile platform by implementing a modular authentication system and developing an intuitive graphical interface.

By expanding beyond Globus Auth to support multiple authentication frameworks, we can enable broader adoption across different scientific communities while maintaining robust security. 
Coupled with a modern GUI that visualizes real-time streaming activity, this enhancement will make SciStream more accessible to researchers—allowing them to focus on their science rather 
than wrestling with complex configurations.

This project will design a user-friendly interface that makes secure scientific data streaming as intuitive as using a cloud storage service. You'll also gain hands-on experience with 
authentication methods used by industry leaders like Google and Facebook, while directly improving access to scientific data.

### **The Specific Tasks of the Project Include**

- Design and implementation of a pluggable authentication system supporting multiple providers (OAuth 2.0, SAML, OpenID Connect, certificate-based auth)
- Development of a modern, responsive GUI using web technologies that provides real-time visualization of system status
- Creation of comprehensive security testing protocols to validate the authentication implementations
- Implementation of session management and secure credential handling within the GUI
- Design of an intuitive interface for managing streaming configurations and monitoring data flows
- Creation of documentation and examples to help facilities integrate their preferred authentication mechanisms
