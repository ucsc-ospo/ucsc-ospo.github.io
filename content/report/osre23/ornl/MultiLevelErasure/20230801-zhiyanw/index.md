---
title: "Reproducible Evaluation of Multi-level Erasure Coding (Midterm)"
subtitle: ""
summary:
authors: [zhiyanw]
tags: ["osre23", "reproducibility"]
categories: [SoR'23]
date: 2023-08-05
lastmod: 2023-08-05
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hi Everyone,

I hope everything goes well! This is my second blog post for my project [Reproducible Evaluation of Multi-level Erasure Coding](/project/osre23/ornl/MultiLevelErasure) under the mentorship of {{% mention john.bent %}}, {{% mention georgea %}}, and Meng Wang. In summary, my project aims to build a platform to reproducibly evaluate the performance and durability of MLEC (Multi-Level Erasure Coding) for large-scale storage systems under different design configurations. The details are in this [proposal](https://docs.google.com/document/d/1dO1aING1QcSB---XklzUjNz0usVh7qWffVGC3GZq2AE/edit?usp=sharing).

In the course of these few weeks, I've completed several tasks to achieve the aim of this project, including
* Literature Review
* Studying the Erasure Coding Simulator and Creating Reproducible Evaluations, with the following policies
  - Clustered/Declustered Local-level SLEC
  - Clustered/Declustered Network-level SLEC
  - MLEC with C/C, C/D, D/C, D/D configuration


## Literature Review

Prior to developing the simulator, my first step was to delve into various literature related to distinct Erasure Coding policies. To understand a simulator for complex Erasure coding policy such as MLEC, I want to start from the simpler EC policies, and then extend my knowledge to more complex ones such as MLEC. Moreover, I also aimed to contrast the durability of MLEC with other comparable EC policies like LRC in my evaluations, making it vital to understand the implementation of these policies.

Over the first week, I read several papers regarding different chunk placement policies regarding erasure coding, including LRC (Local Reconstruction Codes), CL-LRC (Combined Locality for Local Reconstruction Codes), SODP (Single Overlap declustered parity), and MLEC (Multi-Level Erasure Coding). These papers offered a fundamental comprehension of each policy, their respective advantages and drawbacks, and their practical usage in production environments.


## Simulator Reproduction


After gaining some understanding with the papers I read, I started to study the EC simulator by building the simulator myself. I got the MLEC simulator from the mentors. However, the simulator lacks documentation and guides, making it hard for others to reproduce evaluation results. The simulator is also complicated to understand, as it simulates various EC schemes, chunk placements, and rebuild policies, which results in 13,000 LOC. Therefore, my goal is to understand the design and implementation details of the simulator, after which I will create guides for reproducible evaluations.

In order to fully understand the simulator, the best way is to rebuild the simulator by myself. The simulator is designed to mimic disk failures over the span of a year under varying chunk placement policies. Once successfully rebuilt, the simulator will enable me to assess the durability of MLEC in relation to other widely-used chunk placement policies. I followed the given simulator and rewrote it on my own in Python.

Based on the skeleton of the given simulator, I first rebuilt a simple simulator that simulates SLEC (single level erasure coding, in both local and network settings) with clustered parities. With the arguments given, the simulator can run arbitrary numbers of iterations that simulate disk failures in one year. The simulator then collects iterations in which there is a data loss. The ratio of failed iterations to total executed iterations is the durability of the erasure coding policy. This simulation allows us to evaluate the durability of SLEC, laying foundations for later evaluation of MLEC.

Next, I extended my simulator from local-level SLEC implementation by adding more policies. I began by introducing a network-level SLEC policy with clustered parities. This differs slightly from the local-level EC as it necessitates the consideration of factors like network bandwidth within the simulator.

In addition, I have delved deeper into simulating declustered parities and successfully discovered a method to simulate disk failures. Basically, the simulator generates failures within a one-year timeframe and subsequently repairs them using priority queues. The disks associated with stripes experiencing the most failures are given the highest repair priority. With this construction, the simulator is capable of simulating local-level declustered parities, with the ability to specify parameters.

Upon successfully simulating local-level declustered parities, the construction of the simulator for network level declustered parities was rather straightforward. I then validated it using the simulator and math models provided by the mentors. The results perfectly agree with each other, which proves the correctness of my understanding for the SLEC declustered placements. By implementing the simulator myself, I strengthened my understanding of erasure coding designs and the simulation techniques, which equipped me with a solid foundation to continue to reproduce MLEC simulations.

Based on my knowledge gained from implementing SLEC simulators myself, I then reverse-engineered the MLEC simulator provided by the mentors from their MLEC paper. I choose to start from the simplest policy, which is clustered parities in both levels. After spending a considerable time digging into the simulator source codes, I was able to understand the simulation workflows, different repair methods that it implements, and the splitting method that it uses to simulate high durabilities. I then revised my simulator based on my understanding. I also tried to run a few experiments using the same configuration setups as specified in the paper. The results agree well with those in the paper, which verified the success of my reproducing work.


## Technical Issues


In the process of building the MLEC, I've encountered many issues, conceptual or technical. The mentors are super helpful and responsive in the process, so I was able to have steady progress.


## Summary


Overall, I've rebuilt a python simulator for various EC policies, and the simulator can successfully reproduce the results from paper. 


## Next Steps


My next step would be to package the simulator into reprodTrovi artifact, so others can reproduce evaluations on performance and durability of various EC policies, in particular MLEC




