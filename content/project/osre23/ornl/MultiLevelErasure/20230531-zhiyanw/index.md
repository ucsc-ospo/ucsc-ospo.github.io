---
title: "Reproducible Evaluation of Multi-level Erasure Coding"
subtitle: ""
summary:
authors: [zhiyanw]
tags: ["osre23", "reproducibility"]
categories: [SoR'23]
date: 2023-05-31
lastmod: 2023-05-31
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

Hi! My name is Alex, an undergraduate student at the University of Chicago. As part of the [Reproducible Evaluation of Multi-level Erasure Coding](/project/osre23/ornl/MultiLevelErasure), my [proposal](https://docs.google.com/document/d/1dO1aING1QcSB---XklzUjNz0usVh7qWffVGC3GZq2AE/edit?usp=sharing) under the mentorship of **John Bent** and **Anjus George** aims to build a platform to reproducibly evaluate the performance and durability of MLEC (Multi-Level Erasure Coding) for large-scale storage systems under different design configurations. 

To provide some context, Erasure Coding (EC) is a common approach to protect data from disk failures. Data centers nowadays increasingly use Multi-Level Erasure Coding (MLEC), a newly developed erasure coding method that aims to deal with the drawbacks of Single-Level Erasure Coding (SLEC). Despite its increasing popularity, there have not been many systematic studies to analyze and evaluate MLEC, which is the focus of this project. 

The evaluation will primarily be conducted through simulations, since modifying configurations in a real large-scale system is costly and impractical. The expected deliverables of this project will be:
- An MLEC simulator that can reproducibly simulate different configurations of the MLEC system, e.g. coding parameter selection, chunk placement scheme, repair method choice, etc.
- An analysis of the performance and durability tradeoffs between different MLEC design choices based on the evaluation results from the simulation
- Reproduced SLEC evaluation results using existing SLEC simulators
- A comparison between MLEC and SLEC on performance and durability tradeoffs
- Well-written documents and detailed guides on how to reproduce the evaluation results

Our plan is to build the simulator throughout the summer. We hope our simulator and evaluation results can provide designers of large-scale storage systems with valuable insights on choosing the most appropriate erasure coding configuration per their needs.