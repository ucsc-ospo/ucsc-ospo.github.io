---
title: "RAG-ST: Retrieval-Augmented Generation for Spatial Transcriptomics"
summary:
authors: [zeyu]
tags: ["osre25", spatial transcriptomics, generative model, retrieval-augmented generation, machine learning"]
categories: []
date: 2025-06-19
lastmod: 2025-06-19
featured: false
draft: false

image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hi everyone! My name is Zeyu, and I will be working on a project for a retrieval-enhanced generative framework for spatial transcriptomics during Google Summer of Code 2025. My project is called [**RAG-ST: Retrieval-Augmented Generation for Spatial Transcriptomics**](https://ucsc-ospo.github.io/project/osre25/uci/rag-st/) and is supervised by {{% mention ziheng %}}. The goal is to develop a retrieval-enhanced generative framework for predicting spatial gene expression from histological images, making spatial transcriptomics more affordable and easier to implement. [You can view my full proposal here!](https://drive.google.com/file/d/1_yUf1NlVRpBXERCqnOby7pgP4WrWrZsr/view?usp=sharing)

Spatial transcriptomics enables the capture of gene expression profiles with spatial resolution, providing unprecedented insights into cellular organization and the tissue microenvironment. However, its widespread application is limited by high costs and technical complexity. In contrast, histological imaging is inexpensive and widely accessible. If we can accurately predict gene expression from histology images, then high-resolution spatial information can be inferred without costly experiments.

My project will:

- Create a large-scale paired dataset combining HEST histology images with reference gene expression profiles from CellxGene.  
- Design a novel RAG-ST architecture that enables both **interpretable** and **controllable** generation of spatial gene expression.  
- Benchmark RAG-ST against current state-of-the-art models for image-based gene expression inference.  
- Open-source the full codebase and provide comprehensive tutorials to support future research and development.

I am excited to contribute to this project and help broaden access to spatial transcriptomics insights through machine learning–powered predictions!

Zeyu Zou

University of Northeastern Graduate

Zeyu Zou is a graduate student at the University of Northeastern, where he is majoring in Analytics.
