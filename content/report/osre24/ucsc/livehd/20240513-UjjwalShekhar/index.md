---
title: "Hardware Hierarchical Dynamical Systems"
subtitle: "Building an efficient Tree Data Structure used commonly in Hardware Compilers with Benchmarking for Scalability."
summary:
authors: 
  - UjjwalShekhar
tags: ["osre24"]
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
As part of [Micro Architecture Santa Cruz (MASC)](/project/osre23/ucsc/livehd) my [proposal](https://docs.google.com/document/d/1FyQfRVJ2LnPJ9bCBqiylmnc1dOaumed1LQ_N6cK5krw/edit?usp=sharing) under the mentorship of Jose Renau and Sakshi Garg aims to develop a tree data structure under HHDS to replace the current one offered by [LHTree](https://github.com/masc-ucsc/livehd/blob/34eed40f32669bdab2fbf8fbcc65492660ba40df/core/lhtree.hpp#L526) 

The tree data structure is to be optimized for typical AST traversal and queries. Some queries that are made to this tree are much more frequent than others. Thus a flattening policy will be used to optimize the tree for these queries, at the potential cost of becoming slow for the infrequent queries. The tree will be benchmarked for scalability and performance and is expected to outperform the current version of the tree. Once the implementation is complete, the tree will be integrated into the LiveHD core repository.
