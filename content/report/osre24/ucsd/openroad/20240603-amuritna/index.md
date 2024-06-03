---
title: "Building Unit Tests for OpenROAD"
subtitle: "Towards better code coverage!"
summary: ""
authors: [amuritna]
author_notes: ["Undergraduate Electrical Engineering student at Institut Teknologi Bandung"]
tags: ["osre24", uc, reproducibility]
categories: ["chip-design"]
date: 2024-06-03
lastmod: 2024-06-03
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

Hello! My name is Emma and I will be contributing to [OpenROAD](https://theopenroadproject.org/), a tool chain for digital integrated circuit automation (RTL to GDSII), during Google Summer of Code 2024. My project is [Towards Better Coverage: Building Unit Tests of OpenROAD Tools](/project/osre2024/ucsd/openroad), jointly mentored by **Vitor Bandeira** and **Matt Liberty**. The aim of this project is to increase code doverage of OpenROAD by building unit tests for specific features, processes, and tools. [My proposal can be viewed here!](https://drive.google.com/file/d/1Naow453fcZaa8DlEqpkSGoB45odgoqd9/view?usp=sharing)

OpenROAD seeks to create a fully autonomous, open-source tool chain. In particular, it [aims to produce a completed, manufacturable, and tapeout-clean GDSII](https://openroad.readthedocs.io/en/latest/contrib/DeveloperGuide.html#tool-philosophy). As the OpenROAD framework, through continuous development from the hardware community, progresses towards usage in increasingly advanced nodes, better optimization, improved customization, [as well as AI/ML tools](https://www.youtube.com/watch?v=z-yoZuJx2IE), it becomes more and more important to ensure that possible problems are caught and fixed as early as possible.

OpenROAD's test suite should include checks for specific functionalities of each module, impossible values, and corner cases. While various flow and unit tests are already included, there are still many use cases that have not been covered.
