---
title: "StaR"
subtitle: "A Stability-Aware Representation Learning Framework for Spatial Domain Identification"
summary:
authors: 
  - Xindi Wei
tags: ["osre26"]
categories: []
date: 2026-06-18
lastmod: 2026-06-18
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

Hey there, I'm Xindi Wei. I'll be contributing to the StaR project under the mentorship of Ziheng Duan.

# What is the project about?

In spatial transcriptomics, spatial domain identification is a fundamental task aimed at partitioning tissue sections into biologically coherent regions. State-of-the-art Graph Neural Network (GNN) methods have advanced this task significantly, but they share a critical limitation: extreme sensitivity to random initialization.
When evaluating these methods across 1,000 random seeds, several key issues emerge:

(1)The Adjusted Rand Index (ARI) fluctuates drastically, with the worst-to-best gap reaching up to 0.396. 
(2)This seed-induced variance often exceeds the performance differences between competing methods.
(3)Evaluating the same method with different seeds can lead to entirely contradictory conclusions about its utility.

The goal of this project is to develop StaR, a plug-in training framework designed to steer models toward flatter, more reproducible parameter regions, thereby mitigating this extreme seed sensitivity without altering the underlying encoder architecture.

# What do I plan on doing?
The central contribution of this project is the development of StaR, a framework designed to eliminate multi-basin behavior and enforce spatial consistency. My action items to achieve this involve a structural overhaul of the training objective and comprehensive empirical validation:

(1)Implement a Deterministic Spatial Prior
(2)Integrate KL Regularization
(3)Apply Advanced Optimization Techniques
(4)Conduct Comprehensive Benchmarking and Mechanistic Proofs
