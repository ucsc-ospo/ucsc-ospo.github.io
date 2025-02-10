---
title: "SciStream-Rep: An Artifact for Reproducible Benchmarks of Scientific Streaming Applications"
tags: [osre25, reproducibility, networking, data streaming, high performance computing, benchmarking, testbeds, cyber security]
authors: [chungmiranda, fcastro]
author_notes: ["Research Scientist at Argonne National Laboratory", "Systems Developer at Argonne National Laboratory"]
date: 2025-02-10
lastmod: 2025-02-11
---
Data is generated at ever-increasing rates, yet it's often processed more slowly than it's collected. Scientific instruments 
frequently operate below their full capacity—or discard valuable data—due to network bottlenecks, security domain mismatches, 
and insufficient real-time processing capabilities. [SciStream](https://github.com/scistream/scistream-proto) reimagines how 
scientific data moves across modern research infrastructure by providing a framework for high-speed (+100Gbps) memory-to-memory 
streaming that doesn't compromise on security or performance. Whether connecting scientific instruments to analysis clusters or 
bridging across institutional boundaries, SciStream provides the foundation for next-generation scientific workflows. Building 
on our [published research](https://dl.acm.org/doi/abs/10.1145/3502181.3531475), we're now expanding the framework's 
capabilities through open-source development and community collaboration.

### SciStream-SecureBench: A Framework for Benchmarking Security Protocols in Scientific Data Streaming

**Project Idea Description:**

- **Topics**: Security Protocols, Network Performance, Data Streaming, Reproducibility, High-throughput Computing
- **Skills**: Python, Scripting, Linux, Network Protocol Analysis, Containers, Benchmarking tools
- **Difficulty**: Medium
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

While TLS and SSH are the de facto standards for secure data transfer, there's a surprising lack of comprehensive benchmarks characterizing their performance for high-throughput scientific data streaming. This project aims to fill this critical gap by 
developing a reproducible benchmarking framework specifically designed for evaluating security protocols in the context of scientific workflows. Traditional benchmarks focus on general-purpose metrics that don't capture the unique requirements of scientific 
data streaming, such as sustained throughput for bulk transfers and real-time streaming performance.

The Specific Tasks of the Project Include:

- Development of a specialized benchmarking suite that measures security protocol performance metrics relevant to scientific data streaming, including handshake latency, throughput stability, and computational overhead
- Creation of reproducible test scenarios that simulate real scientific instrument data patterns using Chameleon and FABRIC testbeds
- Implementation of automated comparative analysis between TLS and SSH configurations, with emphasis on streaming-specific metrics like time-to-first-byte and sustained throughput
- Design and execution of experiments to quantify the impact of different security configurations on memory-to-memory streaming performance
- Documentation of findings and development of best practices for security protocol selection in scientific streaming applications

### SciStream-StreamBench: Comparative Analysis of Scientific Streaming Frameworks

**Project Idea Description:**

- **Topics**: Data Streaming Protocols, Network Performance, Benchmarking, Distributed Systems, Real-time Computing
- **Skills**: Python, ZeroMQ, EPICS/PVAccess, Linux, Performance Analysis, Visualization
- **Difficulty**: Medium
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

Despite the widespread use of streaming frameworks like ZeroMQ and PVapy in scientific facilities, there's a notable absence of comprehensive benchmarks that evaluate their performance characteristics for high-throughput scientific workflows. This project aims 
to develop a systematic benchmarking methodology to assess these frameworks, focusing on critical metrics such as synchronization overhead, time-to-first-data, and throughput stability. Understanding these characteristics is essential for scientific facilities 
where real-time data access and processing can directly impact experimental outcomes. Recent work with PVapy ([SC'23 paper](https://dl.acm.org/doi/10.1145/3624062.3624610)) demonstrates its potential for streaming experimental facility data to supercomputers, 
further highlighting the need for detailed performance characterization of such frameworks.

The Specific Tasks of the Project Include:

- Design and implementation of a comprehensive benchmarking methodology that captures key performance metrics specific to scientific streaming applications
- Development of a test harness that can simulate real-world conditions including network variability, concurrent streams, and varying data rates using Chameleon and FABRIC testbeds
- Creation of consistent client-server implementations across frameworks (ZeroMQ, PVapy) to ensure fair comparison of their capabilities
- Implementation of automated data collection and analysis pipelines to process performance metrics and identify performance patterns
- Documentation of framework-specific optimizations and configuration guidelines for different scientific streaming scenarios
- Creation of reproducible benchmark artifacts that enable other researchers to validate and build upon the findings

### SciStream-QUIC: Next-Generation Proxy Architecture for Scientific Data Streaming

**Project Idea Description:**

- **Topics**: QUIC Protocol, Network Proxies, Performance Analysis, Protocol Design, Hardware Acceleration
- **Skills**: Python/C++, Network Programming, QUIC (quiche/aioquic), Linux, Performance Analysis
- **Difficulty**: Hard
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

While TCP+TLS proxies are the current standard for secure data streaming, QUIC's integration of transport and security layers promises significant performance benefits for scientific workflows. However, the effectiveness of QUIC-based proxies for 
high-throughput scientific data streaming remains largely unexplored. Initial evaluations of federated streaming architectures ([PAW'23 paper](https://par.nsf.gov/servlets/purl/10380551)) suggest potential benefits of QUIC, but comprehensive benchmarking is 
needed. This project aims to implement and thoroughly benchmark QUIC proxies against traditional TCP+TLS solutions, with special attention to hardware encryption offloading capabilities. The inherent advantages of QUIC's TLS 1.3 integration and multiplexing 
features could potentially revolutionize how we handle secure data streaming in scientific environments.

The Specific Tasks of the Project Include:

- Development of a QUIC-based proxy implementation using modern libraries (quiche, aioquic) optimized for scientific data streaming
- Creation of a comprehensive benchmarking framework comparing QUIC proxies against traditional HTTP/2 and SOCKS5 proxies with TLS
- Implementation of detailed performance metrics collection focusing on connection establishment overhead, multi-stream throughput, and adaptation to network conditions
- Investigation of hardware encryption offloading effectiveness for both QUIC and traditional TLS implementations
- Development of reproducible test scenarios using Chameleon and FABRIC testbeds that simulate real-world scientific data streaming conditions
- Documentation of findings and best practices for deploying QUIC proxies in scientific computing environments

### SciStream-Auth: Modern Authentication and User Interface for Scientific Data Streaming

**Project Idea Description:**

- **Topics**: Authentication Systems, UI/UX Design, Security Integration, Scientific Computing
- **Skills**: Python, Web Development (React/Vue), OAuth 2.0/SAML, Security Analysis
- **Difficulty**: Medium
- **Size**: Large (350) hours
- **Mentors:** {{% mention chungmiranda %}}, {{% mention fcastro %}}

In today's scientific computing landscape, authentication and user experience often create barriers to adoption rather than enabling seamless collaboration. While SciStream excels at high-speed data transfer, its reliance on a single authentication provider and 
command-line interface can limit its accessibility. This project aims to transform SciStream into a more versatile platform by implementing a modular authentication system and developing an intuitive graphical interface. By moving beyond Globus Auth to support 
multiple authentication frameworks, we can enable broader adoption across different scientific communities while maintaining robust security. Coupled with a modern GUI that visualizes real-time streaming state, this enhancement will make SciStream more 
accessible to researchers who need to focus on their science rather than wrestling with complex configurations.

The Specific Tasks of the Project Include:

- Design and implementation of a pluggable authentication system supporting multiple providers (OAuth 2.0, SAML, OpenID Connect, certificate-based auth)
- Development of a modern, responsive GUI using web technologies that provides real-time visualization of system status
- Creation of comprehensive security testing protocols to validate the authentication implementations
- Implementation of session management and secure credential handling within the GUI
- Design of an intuitive interface for managing streaming configurations and monitoring data flows
- Creation of documentation and examples to help facilities integrate their preferred authentication mechanisms
