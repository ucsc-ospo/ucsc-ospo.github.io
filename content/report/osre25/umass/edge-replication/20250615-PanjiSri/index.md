---
title: "Developing an Open Testbed for Edge Replication System Evaluation"
# subtitle: "Since OSRE 2023 we ask student contributors to blog!"
summary: "Creating a comprehensive framework to enable fair comparison of edge replication systems and coordination protocols through standardized benchmarking tools and realistic workload simulation."
authors: [PanjiSri]
tags: [osre25, reproducibility, distributed systems, edge, coordination protocols]
categories: []
date: 2025-06-15
lastmod: 2025-06-15
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [osre]
---

Hi, I'm Panji. I'm currently contributing to the [Open Testbed for Reproducible Evaluation of Replicated Systems at the Edges](/project/osre25/umass/edge-replication/) under the mentorship of Fadhil I. Kurnia. You can find more details on the project proposal [here](https://drive.google.com/file/d/1CFT5CJJXbQlVPz8_A9Dxkjl7oRjESdli/view?usp=sharing).

The primary challenge we're addressing is the current difficulty in fairly comparing different edge replication systems. To fix this, we're trying to build a testing platform with four key parts. We're collecting real data about how people actually use edge services, creating a tool that can simulate realistic user traffic across many locations, building a system that mimics network delays between hundreds of edge servers, and packaging everything into an open-source toolkit.

This will let researchers test different coordination methods like EPaxos, Raft, and others using the same data and conditions. We hope this will help provide researchers with a more standardized way to evaluate their systems. We're working with multiple programming languages and focusing on making complex edge computing scenarios accessible to everyone in the research community.

One of the most interesting aspects of this project is tackling the challenge of creating realistic simulations that accurately reflect the performance characteristics different coordination protocols would exhibit in actual edge deployments. The end goal is to provide the research community with a standardized, reproducible environment for edge replication.