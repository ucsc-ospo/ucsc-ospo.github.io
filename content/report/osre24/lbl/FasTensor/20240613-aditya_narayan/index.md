---
title: Stream Processing support for FasTensor 
authors: 
- aditya_narayan
- bindong
- kwu
tags: [osre24, uc, "FasTensor", "scientfic computing", "osre2024", "HPC", "tensor processing", "linear algebra", "API design", "C++",  "LBNL", "Lawrence Berkeley National Lab"]
categories: ["GSoC'24", "gsoc2024","osre2024"]
date: 2024-06-13
lastmod: 2024-06-13
featured: false
draft: false
user_groups:
- 2024 Contributors

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---


Hi, I'm Aditya Narayan,👋

I'm a frequent visitor to the town square of theoretical CS, operations (Ops), and robust high-performance systems. Sometimes I indulge myself with insights on [Computing and Biology](https://www.science.org/doi/10.1126/science.aam9868), and other times I enjoy the accounts of minefield experiences in the [systems world](https://www.youtube.com/watch?v=tDacjrSCeq4). Luckily, this summer, OSRE offered an opportunity that happened to be at the perfect intersection of my interests.

This summer, I will be working on a scientific computing library called FasTensor that offers a parallel computing structure called Stencil, widely popular in the scientific computing world to solve PDEs for Physical Simulations and Convolutions on Signals, among its many uses.
I am excited to introduce my mentors, Dr. {{% mention bindong %}} and Dr. {{% mention kwu %}} of the [Scientific Data Management Group](https://crd.lbl.gov/divisions/scidata/sdm/) at Lawrence Berkeley National Laboratory (LBNL). They bring invaluable expertise to the project. 

They recognized the need for a tensor processing library that provided dedicated support for big datasets with inherent structural locality, often found in the scientific computing world, which was lacking in popular open-source MapReduce or Key-Value based frameworks.

More often than not, the operations performed on these datasets are composed of computations involving neighboring elements. This motivated the development of the FasTensor library.

I will be working on providing a Stream Processing interface that enables online data processing of large-scale datasets as they arrive from Data Producers. The project focuses on offering rich interfaces for managing and composing streams, supporting common scientific data formats like HDF5, and integrating fault tolerance and reliability mechanisms.

I am thrilled to work on the FasTensor project because I believe it has the potential to make a significant impact by enabling researchers to implement a rich set of computations on their big datasets in an easy and intuitive manner.

After all, FasTensor has just one simple paradigm: A -> Transform(F(x), B),

and it handles all the behind-the-scenes grunt work of handling big datasets so you can focus on your research.

Stay tuned for updates and feel free to [collaborate](https://github.com/BinDong314/FasTensor)!
