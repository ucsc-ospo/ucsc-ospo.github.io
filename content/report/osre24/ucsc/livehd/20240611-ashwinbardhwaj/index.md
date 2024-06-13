---
title: "LiveHD: Benchmarking LLMs that Generate Verilog/Chisel Modules From Natural Language"
subtitle: ""
summary:
authors: 
  - ashwinbardhwaj
tags: ["osre24", uc, reproducibility, LLM, HDL]
categories: []
date: 2024-05-14
lastmod: 2024-05-14
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
Hi everyone!

I'm Ashwin Bardhwaj, currently pursuing a bachelors in Electrical Engineering and Computer Science at UC Berkeley. I was recently involved in a project to implement a secure hardware encryption enclave in Verilog. That's why I was excited to work with the MASC group to evaluate how existing generalized LLMs (such as ChaptGPT 4 or StarCoder) can generate accurate Verliog/Chisel code from English and assist in the hardware development process. 

As part of [Micro Architecture Santa Cruz (MASC)](/project/osre23/ucsc/livehd) my [proposal](https://drive.google.com/file/d/1Fnr85lqrTs7OBohfHfSZI2K3wZU3zJm0/view?usp=sharing) under the mentorship of {{% mention renau %}} and {{% mention sgarg3 %}} looks to create a suite of benchmark programs for [HDEval](https://github.com/masc-ucsc/hdeval).

The deliverable of this project is to create multiple large HDL benchmarks along with a respective set of prompts. Using yosys to implement Logic Equivalence Check, we are able to prove through formal verification that the generated code will exhibit the same behavior as the benchmark. In addition, we can also consider the performance and resource utilization of the generated code as a metric. 
