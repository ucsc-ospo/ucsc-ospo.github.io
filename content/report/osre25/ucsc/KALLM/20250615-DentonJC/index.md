---
title: "Kolmogorov-Arnold-based Transformer for LLMs"
subtitle: "Implementation, Evaluation and Benchmarking"
summary: "Developing efficient and interpretable LLMs by integrating Kolmogorov-Arnold-based modules into Transformers to reduce parameters and maintain performance."
authors: 
  - DentonJC
tags: ["osre25"]
categories: ["machine-learning"]
date: 2025-06-15
lastmod: 2025-06-15
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Architecture of the Transformer with suggested modifications."
  focal_point: "Center"
  preview_only: false
---

Project: [KALLM](/project/osre25/UNL/KALLM) 

Proposal: [proposal](https://krutsylo.neocities.org/share/pdf/KALLM_Public.pdf)

Mentors:     

- Sai Suman Lamba Karanam
- Prof. Zahmeeth Sakkaff

I am modifying existing large language models to make them more efficient by replacing some of their layers with Kolmogorov-Arnold Network (KAN) modules. These KAN layers use compact univariate polynomial approximations, which can reduce parameter count and improve interpretability. The project explores how to integrate these layers into Transformers, and how far we can push this idea by combining or stacking KAN modules with different polynomial bases. The goal is to keep performance competitive while lowering computational costs.

Beyond just speeding up training, I am exploring several other promising directions. One is testing whether transfer learning remains effective when replacing the linear layers of a pretrained LLM with KAN modules, or when swapping between different KAN configurations. I am also considering curriculum learning strategies that gradually increase KAN complexity during training. I have studied all major KAN implementations and early experiments with a custom Transformer architecture show encouraging results. However, I have found that most LLMs rely on functional-style activation definitions in PyTorch, which makes it difficult to build a universal wrapper. Because of this, KAN-based models will likely need to be integrated manually on a case-by-case basis.
