---
title: "Reproducible Evaluation of Multipath Network Protocols"
summary: "As mobile devices with dual WiFi and cellular interfaces become widespread, network protocols have been developed that utilize the availability of multiple paths. This project is about developing a framework for rigorous, repeatable, and comprehensive evaluations of multipath protocols."
authors: ["Ilknur Aydin"]
author_notes: ["Associate Professor, Computer Systems, Farmingdale State College"]
tags: ["osre23", "reproducibility"]
date: 2023-02-16T00:00:00Z
lastmod: 2023-02-16T00:00:00Z
---

Lead Mentor: [Ilknur Aydin](mailto:aydini@farmingdale.edu) 

As mobile devices with dual WiFi and cellular interfaces become widespread, network protocols have been developed that utilize the availability of multiple paths. However, the relative effectiveness of these protocols is highly dependent on the characteristics of the network (including the relationship between the two paths, which are often not independent). Researchers typically evaluate a multipath protocol for a small set of network scenarios, which vary from one publication to the next. It is therefore difficult to get a good picture of how different protocols perform in a range of settings.


### Framework for repeatable, direct comparison of multipath transport protocols

* **Topics**: Computer networks, wireless systems
* **Skills**: Linux, networking, data analysis and visualization, writing
* **Difficulty**: Large
* **Size**: 350 hours
* **Mentor(s)**: [Ilknur Aydin](mailto:aydini@farmingdale.edu) and [Fraida Fund](mailto:ffund@nyu.edu) 

In single-path congestion control, the [Pantheon](https://pantheon.stanford.edu/) work created a reference set of executable benchmarks that researchers could use to evaluate novel congestion control designs against existing work in a wide range of the scenarios. This project seeks to achieve something similar for multipath protocols, using publicly available networking testbeds like [FABRIC](https://fabric-testbed.net/). For this project, the participant will:


* Prepare a set of network benchmarks for multipath protocols, using live network links, real link traces, and emulated scenarios
* Develop an experiment using the benchmarks to evaluate existing multipath protocol implementations
* Prepare materials that researchers can use to evaluate novel multipath protocols against the others in the benchmark
