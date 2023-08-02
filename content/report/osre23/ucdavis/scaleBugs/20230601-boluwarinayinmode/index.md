---
title: "ScaleBugs: Reproducible Scalability Bugs"
subtitle: ""
summary:
authors: [boluwarinayinmode, imzahra]
tags: ["osre23"]
categories: ["SummerofReproducibility23"]
date: 2023-06-01
lastmod: 2023-08-02
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

Hello! As part of the [ScaleBugs](/project/osre23/ucdavis/scalebugs/) project our proposals ([proposal](https://drive.google.com/file/d/17iANa5ei_gguZsGGwR1sfPHOoJysnNsf/view?usp=sharing) from {{% mention boluwarinayinmode %}} and [proposal](https://drive.google.com/file/d/199ZsiWHXsLYbSJ896vaf8tjrYs23P5xN/view?usp=sharing) from {{% mention imzahra %}}) under the mentorship under the mentorship of {{% mention rubio %}},{{% mention haryadi %}} and {{% mention hnzhu %}} aims to build a dataset of reproducible scalability bugs by analyzing bug reports from popular distributed systems like Cassandra, HDFS, Ignite, and Kafka. For each bug report, we will analyze whether the reported bug is influenced by the scale of the operation, such as the number of nodes being used or a number of requests. The resulting dataset will consist of bug artifacts containing the buggy and fixed versions of the scalability system, a reproducible runtime environment, and workload shell scripts designed to demonstrate bug symptoms under different scales. These resources will help support research and development efforts in addressing scalability issues and optimizing system performance.
