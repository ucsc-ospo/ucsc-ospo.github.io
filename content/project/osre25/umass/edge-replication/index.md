---
title: "Open Testbed for Reproducible Evaluation of Replicated Systems at the Edges"
authors: [fadhil]
author_notes: ["University of Massachusetts"]
tags: ["osre25", "reproducibility", "distributed systems", "edge", "coordination protocols"]
date: 2025-02-15
lastmod: 2025-02-15
---

## Project Description

- **Topics**: Distributed systems
- **Skills**: Java, Go, Python, Bash scripting, Linux, Docker.
- **Difficulty**: Hard
- **Size**: Large (350 hours)
- **Mentors**: [Fadhil I. Kurnia](mailto:fikurnia@cs.umass.edu)

Replication is commonly employed to improve system availability and reduce latency. By maintaining multiple copies, the system can continue operating even if some replicas fail, thereby ensuring consistent availability. Placing replicas closer to users further decreases latency by minimizing the distance data must travel. A typical illustration of these advantages is a Content Delivery Network (CDN), where distributing content to edge servers can yield latencies of under 10 milliseconds when users and contents are in the same city.

In recent times, numerous edge datastores have emerged, allowing dynamic data to be served directly from network-edge replicas. Each of these replicated systems may employ different coordination protocols to synchronize replicas, leading to varied performance and consistency characteristics. For instance, Workers KV relies on a push-based coordination mechanism that provides eventual consistency, whereas Cloudflare Durable Objects and Turso deliver stronger consistency guarantees. Additionally, researchers have introduced various coordination protocols—such as SwiftPaxos, EPaxos, OPaxos, WPaxos, Raft, PANDO, and QuePaxa—each exhibiting its own performance profile, especially when being used in geo-distributed deployment.

This project aims to develop an open testbed for evaluating replicated systems and their coordination protocols under edge deployment. Currently, researchers face challenges in fairly comparing different replicated systems, as they often lack control over replica placement. Many previous studies on coordination protocols and replicated systems relied on mock implementations, particularly for well-known systems like Dynamo and Spanner, which are not open source. An open testbed would provide a standardized environment where researchers can compare various replicated systems, classes of coordination protocols, and specific protocol implementations using common benchmarks. Since the performance of replicated systems and coordination protocols varies depending on the application, workload, and replica placement, this testbed would offer a more systematic and fair evaluation framework. Furthermore, by enabling easier testing and validation, the testbed could accelerate the adoption of research prototypes in the industry.


## Project Deliverables
- Compilation of traces and applications from various open traces and open benchmarks.
- Distributed workload generator to run the traces and applications.
- Test framework to simulate latency of 100s of edge servers for measurement.
- Open artifact of the traces, applications, workload generator, and test framework, published on Github.
