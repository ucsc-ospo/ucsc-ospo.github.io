---
title: "Building a Framework to Benchmark Different Placement Algorithms in a Distributed System"
# subtitle: "Since OSRE 2023 we ask student contributors to blog!"
summary: "This is now common practice and an efficient way to track activities within OSRE projects. Include links to proposals, presentations, reports, and experience."
authors: [mchan]
tags: [osre26, reproducibility, distributed systems, edge, coordination protocols]
categories: []
date: 2026-06-09
lastmod: 2026-06-09
featured: false
draft: false
math: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [osre]
---

Hey there, I'm Michael. I'll be contributing to the [Reconfigurable and Placement-Aware Replication for Edge Systems](/project/osre26/umass/edge-replication/) project under the mentorship of {{% mention fadhil %}}. This project is a continuation of last year's OSRE program called [Open Testbed for Reproducible Evaluation of Replicated Systems at the Edges](/project/osre25/umass/edge-replication/). The project started off as a glue framework to evaluate the performance (throughput capacity and latency) of different consensus protocols under the same workload. This summer, I'll be extending the framework to support the evaluation of different placement algorithms.

## What is the project about?
In a distributed system, an object (any arbitrary data) is replicated across multiple nodes. If latency is the only factor that is considered, then the most obvious solution is to replicate the same object to all nodes in the system. This solution is very costly and is therefore undesirable. The next option is then to design a placement algorithm to determine which nodes the object should be placed in. There are many criteria that could be used to determine replica placement, such as:

1. How are user demands distributed across the world? Which areas have the highest demand?
2. How much resources does each node have in terms of network bandwidth, compute capacity, storage capacity, etc?
3. What consensus protocol is being used for the system in question? How much coordination is done between nodes?

The goal of this project is to extend [Distrobench](https://distrobench.org/) with the ability to benchmark different placement algorithms under the same workload.

## What do I plan on doing?
Currently existing implementations of consensus protocols can be categorized into three types:

1. Consensus protocols that don't implement the ability to move the object placement (Type 1)
2. Consensus protocols with the ability to move object placement, but no placement algorithm to effectively choose which nodes to place the object in (Type 2)
3. Consensus protocols that supports object placement and have a placement algorithm (Type 3)

My action item is to build an abstraction layer that allows different consensus protocols to be tested with arbitrary placement algorithms. The solution that I am thinking of right now is as follows:
1. (Type 1) Each protocols would be treated as part of the workload for the placement algorithms. In this case, the running protocols would be stopped and then re-run with a different configuration to simulate a different object placement.
2. (Type 2) The external placement algorithm will determine which nodes to place the object in. The new object placement will then be set using an API to the protocol implementation.
3. (Type 3) Simulate the workload for the protocol implementation, trigger an object placement on the protocol, then evaluate the change in performance. No external placement algorithm is involved in this process.

The benchmark's purpose is to answer the question of:
> How would placement algorthm $x$ with workload $y$ perform across all the different consensus protocols? At what [consistency model](https://jepsen.io/consistency/models) (linearizability, sequential, eventual, etc) does the algorithm work best?

My full proposal can be found [here](https://drive.google.com/file/d/1IGihqPVLfTI01MJ-qYm1Tth8T5KUeSic/view?usp=sharing).
