---
title: "Reproducible CXL Emulation"
authors: ["Mujahid Al Rafi", "Luanzheng Guo"]
author_notes: ["Graduate Student Researcher, UC Merced", "Computer Scientist, Pacific Northwest National Laboratory"]
tags: ["reproducibility", "osre26", "CXL emulation", "memory systems", "uc", "PNNL", "multi-host systems"]
date: 2026-01-30
lastmod: 2026-01-30
---

Compute Express Link (CXL) is an emerging memory interconnect standard that enables shared, coherent memory across CPUs, accelerators, and multiple hosts, unlocking new possibilities in hyperscale, HPC, and disaggregated systems. However, because access to real multi-host CXL hardware is limited, it is difficult for researchers and students to experiment with, evaluate, and reproduce results on advanced CXL topologies.
OCEAN (Open-source CXL Emulation At Hyperscale) [https://github.com/cxl-emu/OCEAN] is a full-stack CXL emulation platform built on QEMU that enables detailed emulation of CXL 3.0 memory systems, including multi-host shared memory pools, coherent fabric topologies, and latency modeling. This project will create reproducible experiment pipelines, automated deployment workflows, and user-friendly tutorials so that others can reliably run and extend CXL emulation experiments without requiring specialized hardware.

### Reproducible CXL Emulation for Multi-Host Memory Systems

Streamline multi-host CXL emulation without specialized hardware.

- **Topics:** `CXL emulation` `Memory Systems` `Reproducibility`
- **Skills:** C/C++, Virtualization (QEMU), Scripting, Performance Modeling
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** [Mujahid Al Rafi](mailto:mrafi@ucmerced.edu), [Luanzheng "Lenny" Guo](mailto:lenny.guo@pnnl.gov)
  
Tasks:
- Create automated deployment scripts and configuration templates for OCEAN-based CXL emulation topologies (single-host and multi-host).
- Develop a standardized experiment harness for running memory performance benchmarks (e.g., OSU micro-benchmarks, STREAM-style tests) in emulated CXL environments.
- Build reproducible experiment pipelines that others can run to evaluate latency, bandwidth, and scaling properties of CXL memory systems.
- Produce tutorials, documentation, and reproducibility artifacts to guide new users through setup, execution, and analysis.
- Package and contribute all scripts, configurations, and documentation back to the OCEAN open-source repository.



### Exploring Security and Isolation in CXL-Based Memory Systems

Investigate security and isolation properties of CXL-based memory systems using software emulation.

- **Topics:** `CXL Systems` `Security` `Memory Isolation` `Side Channel` `Emulation`
- **Skills:** C/C++, Virtualization (QEMU), Scripting, Computer Architecture, Security
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** [Mujahid Al Rafi](mailto:mrafi@ucmerced.edu), [Luanzheng "Lenny" Guo](mailto:lenny.guo@pnnl.gov)

Tasks:
- Study the CXL memory model and fabric architecture to identify potential security and isolation risks in multi-host shared memory environments (e.g., contention, timing variation, and resource interference).
- Set up multi-host or multi-VM CXL emulation environments using OCEAN that mimic realistic multi-tenant deployments.
- Design and implement reproducible micro-benchmarks to measure timing, bandwidth contention, or observable interference through shared CXL memory pools.
- Analyze how fabric configuration choices (e.g., topology, latency injection, memory partitioning, or allocation policies) affect isolation and leakage behavior.
- Explore and prototype mitigation strategies—such as memory partitioning, throttling, or policy-driven allocation—and evaluate their effectiveness using the emulation platform.
