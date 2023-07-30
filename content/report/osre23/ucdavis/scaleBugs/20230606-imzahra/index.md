---
title: "ScaleBugs: Reproducible Scalability Bugs"
subtitle: ""
summary: ""
authors: ["imzahra"]
tags: ["osre23"]
categories: ["SummerofReproducibility23"]
date: 2023-06-06
lastmod: 2023-06-06
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

Hi! I'm Zahra, an undergraduate at Universitas Dian Nuswantoro, Indonesia. 
As part of the [ScaleBugs](/project/osre23/ucdavis/scalebugs/) my [proposal](https://drive.google.com/file/d/199ZsiWHXsLYbSJ896vaf8tjrYs23P5xN/view?usp=sharing) under the mentorship of {{% mention rubio %}} and {{% mention haryadi %}} aims to build a dataset of reproducible scalability bugs. 

Analyzing through the existing bug reports for popular distributed systems, such as Cassandra, HDFS, Ignite, and Kafka. For each bug report, we will analyzing whether the reported bug is influenced by the scale of the operation, such as the number of nodes being used. With the collected scale-dependent bugs, we will design specific workloads to replicate those scalability issues. These workloads will be carefully crafted to activate certain system functionalities under different configurations, such as varying the number of nodes. By doing so, we aim to demonstrate how the system's functionality is affected as the number of nodes increases.