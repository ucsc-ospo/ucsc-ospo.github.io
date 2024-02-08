---
title: "Turn on, Tune in, Listen up: Maximizing Side-Channel Recovery in Cross-Platform Time-to-Digital Converters"
authors: [drichmond, tsheaves]
author_notes: ["Assistant Professor of Computer Science & Engineering at UC Santa Cruz", "PhD Student at UC Davis"]
tags: ["osre24", "uc"]
date: 2024-02-08
lastmod: 2024-02-08
---

[Turn on, Tune in, Listen Up](https://github.com/KastnerRG/PL-Sensors) Is an open-source framework for implementing voltage flucturation sensors in FPGA devices for use in side-channel security research. Side-channels are an ever present hardware security threat. The reconfigurability of FPGAs significantly broadens the side-channel attack surface in many cloud heterogeneous systems. We have developed a highly tunable side-channel sensor, which significantly improves side-channel attack time and resolution in multiple contexts. Concurrent users sharing the same device may attack one another through the power side-channel (check out our paper https://dl.acm.org/doi/abs/10.1145/3543622.3573193), while consecutive users may attack one another through measurement of the physical wear-out state of the FPGA device (check out our paper https://arxiv.org/abs/2303.17881). We have demonstrated these attack surfaces on both Intel (Altera) and AMD (Xilinx) platforms. Currently, our open-sourced sensor design and side-channel analysis flow is limited to AMD devices. We are seeking CSE/CS/CE/ECE researchers interested in FPGA design, heterogeneous computing and/or hardware security to combine our Intel and AMD side-channel sensors into a unified attack framework and comparing capabilities between vendors.

### Open-source sensor repository updates

- **Topics:**  `Hardware security`, `cloud security`, `heterogeneous computing`, `temporal and spatial side-channels`
- **Skills:**  Experience with GitHub, FPGA development (AMD or Intel), and Python
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** [Dustin Richmond](mailto:drichmond@ucsc.edu), [Tyler Sheaves](mailto:tsheaves@ucdavis.edu)

Update existing open-source voltage fluctuation sensor to support both AMD and Intel devices. Currently our repository exclusively supports AMD FPGAs. We have added new features to our sensor and have demonstrated an implementation on Intel. We would like to consolidate this work into a unified repository containing side-channel analysis demonstrations using open-source target benchmark designs.

Specific tasks:
- Adapt existing tooling scripts to support multiple vendor tool flows.
- Adapt existing test infrastructure to target multiple SoC-type FPGA platforms (i.e. DE10-Nano, Pynq Z2, etc.).
- Evaluate cross-platform sensor architecture on a collection of benchmark designs. Demonstrate each benchmark using a cross-platform unified side-channel analysis framework.
- Draw a comparison between sensor implementations on different architectures.