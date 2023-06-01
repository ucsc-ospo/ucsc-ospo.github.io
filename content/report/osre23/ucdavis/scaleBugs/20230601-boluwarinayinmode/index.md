---
title: "ScaleBugs: Reproducible Scalability Bugs"
subtitle: ""
summary:
authors: [boluwarinayinmode]
tags: ["osre23"]
categories: ["SummerofReproducibility23"]
date: 2023-06-01
lastmod: 2023-06-01
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

As part of the [ScaleBugs](/project/osre23/ucdavis/scalebugs/) my [proposal](https://drive.google.com/file/d/17iANa5ei_gguZsGGwR1sfPHOoJysnNsf/view?usp=sharing) under the mentorship of {{% mention rubio %}} and {{% mention haryadi %}} aims to build a dataset of reproducible scalability bugs by analyzing bug reports from popular distributed systems like Cassandra, HDFS, Ignite, and Kafka. The focus is on identifying bugs that are dependent on the scale of the run, such as the number of nodes, file sizes, and request numbers. The resulting dataset will consist of bug artifacts containing the buggy and fixed versions of the scalability system, a reproducible runtime environment, and workload shell scripts designed to demonstrate bug symptoms under different scales. These resource will help support research and development efforts in addressing scalability issues and optimizing system performance.
