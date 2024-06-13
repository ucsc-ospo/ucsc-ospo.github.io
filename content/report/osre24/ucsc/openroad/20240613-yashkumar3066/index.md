---
title: "Memory Compiler in OpenROAD"
subtitle: "Building a DFFRAM-based Memory Compiler and integrating it to the OpenROAD-flow-scripts"
summary:
authors: 
  - yashkumar306
tags: ["osre24", ucospo, gsoc24, openroad]
categories: [chip-design]
date: 2024-06-13
lastmod: 2024-06-13
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
Greetings! I'm Yash Kumar working on the [OpenROAD Memory Compiler Project](project/osre24/openroad/openroad/) for which my [proposal](https://docs.google.com/document/d/1EGxLSYzVWMtBHmT6m3QQTBA_rqJnMB9qfqR51GSb71k/edit?usp=sharing) under the mentorship of [Matt](/author/matt-liberty/) and [Austin](/author/austin-rovinski/) aims to enhance the OpenROAD flow by integrating a DFFRAM generator that extensively uses the OpenDB database to build and layout various memory components like bits, bytes, and 32x32 configurations and more. Taking inspiration from the work of the [AUCOHL repository’s DFFRAM memory compiler](https://github.com/AUCOHL/DFFRAM),

The goal is to develop a DFF/Latch-based RAM that utilizes standard cell libraries. The compiler will generate different views (HDL netlist, functional models, LEF, DEF, Timing, etc.) for specified size configurations, targeting compact design and optimal routing. The compiler should work across various PDKs satrting with Sky130. My initial works tries to test the Bit and Byte level design.
