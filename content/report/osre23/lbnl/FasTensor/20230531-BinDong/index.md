---
title: "FasTensor"
subtitle: "FasTensor+GPU"
summary:
authors: [bindong]
tags: ["osre23"]
categories: []
date: 2023-05-31
lastmod: 2023-05-31
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

As part of the [PROJECTNAME](/project/osre23/ORGANIZATION/PROJECTNAME), we will develop generic Tensor computing libraries on GPU. Tensor based computing is needed by scientific applications and advanced AI model training. Most tensor libraries are hand customized and optimized on GPU, and most of they only serve one kind of application. For example, TensorFlow is only optimized for AI model training.  Optimizing generic tensor computing libraries on GPU can benefit wide applications. Our [FasTensor](https://sdm.lbl.gov/fastensor/), as a generic tensor computing library, can only work efficiently on CPU now.  How to run the FasTensor on GPU is still none-explored work. Research and development challenges will include but not limited to: 1) how to maintain structure-locality of tensor data on GPU; 2) how to reduce the performance loss when the structure-locality of tensor is broken on GPU. 

