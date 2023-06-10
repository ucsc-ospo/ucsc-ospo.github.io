---
title: "[FLASHNET]: Leveraging ML-augmented I/O in Linux"
subtitle: ""
summary: ""
authors: ["Justin08784"]
author_notes: ["Student at the University of Chicago"]
tags: ["osre23"]
categories: [GSoC'23]
date: 2023-05-30
lastmod: 2023-05-30
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

Hi! I'm Justin, an undergraduate at the University of Chicago. As part of the [Flashnet](/project/osre23/uchicago/flashnet) project my [proposal](https://drive.google.com/file/d/1gsNaYUYOgdN2ilpyPOmI7jjLeoZh219J/view) under the mentorship of
**Daniar Kurniawan** and {{% mention haryadi %}} aims to port the Flashnet model into the Linux kernel. 

In this attempt, I will borrow architecture/design choices from LAKE (to take advantage of its integration of ML-focused hardware acceleration in the kernel) and evaluation criteria from LinnOS to test for model inference accuracy. I also plan to support latency "bucket" inference output to improve accuracy. Ultimately, my goal is to gain further insight into best practices for integrating ML models into real-life operating systems like Linux and to inform general design choices for the Flashnet pipeline. 