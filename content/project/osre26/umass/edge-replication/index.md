---
title: "Reconfigurable and Placement-Aware Replication for Edge Systems"
authors: [fadhil]
author_notes: ["University of Massachusetts"]
tags: ["osre26", "reproducibility", "distributed systems", "edge", "coordination protocols"]
date: 2026-01-31
lastmod: 2026-01-31
---

## Project Description

- **Topics**: Distributed systems
- **Skills**: Rust, Java, Go, Python, Bash scripting, Linux, Docker.
- **Difficulty**: Hard
- **Size**: Large (350 hours)
- **Mentors**: [Fadhil I. Kurnia](mailto:fikurnia@cs.umass.edu)

Modern replicated systems are typically evaluated under static configurations with fixed replica placement. However, real-world edge deployments are highly dynamic: workloads shift geographically, edge nodes join or fail, and latency conditions change over time. Our existing testbed provides reproducible evaluation for replicated systems but lacks support for dynamic reconfiguration and adaptive edge placement policies.

This project extends the existing open testbed to support:

1. Dynamic Replica Reconfiguration
   - Membership changes (add/remove replicas)
   - Leader migration and shard movement
   - Online reconfiguration cost measurement (latency spikes, recovery overhead, state transfer cost)

2. Edge-Aware Placement Policies
   - Demand-aware placement based on geographic workload skew
   - Latency-aware and bandwidth-aware replica selection
   - Comparison of static vs. adaptive placement strategies
   - Evaluation under real-world latency matrices (e.g., US metro-level or cloud region traces)

3. What-if Simulation Framework
   - Replay workload traces with time-varying demand
   - Simulate hundreds of edge sites with realistic network conditions
   - Quantify trade-offs between consistency, availability, reconfiguration overhead, and cost

The outcome will be an [open-source framework](https://distrobench.org) that enables researchers to evaluate not only steady-state replication performance, but also how systems behave under churn, scaling events, and demand shifts. They are central challenges in real edge environments.

### Expected Deliverables

- Reconfiguration abstraction layer (API for membership & placement changes)
- Placement policy plugin framework (k-means, facility-location heuristics, latency-minimizing, cost-aware)
- Trace-driven dynamic workload engine
- Public benchmark scenarios and reproducible experiment scripts
- Artifact-ready documentation and evaluation report