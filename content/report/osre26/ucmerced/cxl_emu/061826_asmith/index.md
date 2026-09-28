---
title: "Optimizing and Evaluating CXL in the Memory Hierarchy with OCEAN"
subtitle:
summary: "Introducing my project to enable the optimization and placement of
CXL within the memory hierarhcy by using and improving OCEAN, an open-sourced
QEMU-backed infrastructure for CXL emulation."
authors:
  - aldsmith
  - kakulo
tags: ["osre26", "pnnl", "CXL emulation", "Memory Systems"]
categories: []
date: 2026-06-18
lastmod: 2026-06-18
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "Smart"
  preview_only: false
---

Howdy! My name is {{% mention aldsmith %}}, a graduate student at the
University of Wisconsin - Madison with a focus on computer architecture. As a
part of Google Summer of Code (GSoC) under the UC OSPO organization, my
project focuses on both contributing and using Open-source CXL Emulation At
Hyperscale ([OCEAN](https://github.com/fam-emu/OCEAN)), an open-source QEMU-based CXL emulation platform, for memory systems research.

The increase in demand for compute resources under HPC+ML applications (e.g.,
LLMs, quantum chemistry), overcoming memory bottlenecks is increasingly
important to fulfill compute demand. CXL offers one such way to do this by
pooling memory and thus increasing bandwidth. However, the availability of CXL
hardware is very limited, and early-design space exploration via simulators
(e.g., gem5) takes prohibivtively long. This is where OCEAN has benefits, as
it allows CXL studies while not being prohibitively expensive and being fairly
accurate.

Under the mentorship of {{% mention kakulo %}}, I will utilize OCEAN to perform studies on evaluating optimal placement of CXL onto the memory hierarchy. To solve this problem, we need to answer two key questions:
1. Where would CXL provide the most optimal performance in the memory
hierarchy? Is it more optimal to have CXL to serve as a cache or main memory?
2. Given where CXL-backed memory lies in the hierarchy, how should we tune
knobs so that it gives optimal performance (e.g., topology, capacity,
injection latency)

This project wil fulfill those goals by improving the documentation and
reproducability (e.g., allowing users to build their own environments and VMs,
implementing CI/CD tests) of OCEAN, improving OCEAN's infrastructure such as
better statistics and improving the backend CXLMemSim tool, and adding
tuneable knobs to allow experimentation in where to place, and how to
configure, CXL for the memory hierarchy.

I'm excited to improve the tooling infrastructure of CXL and apply it memory
systems research! You can find my full project proposal
[here](https://drive.google.com/file/d/1HwnIWEBEmAdWRDQng8Wom9rSCiWHuUaf/view?usp=sharing).
