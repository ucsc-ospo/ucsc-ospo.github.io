---
title: "Final Report — RAG-ST: Retrieval-Augmented Generation for Spatial Transcriptomics"
summary: "Final report for the RAG-ST project under OSRE 2025, focusing on predicting spatial gene expression from histology images using retrieval-augmented generation."
authors:
  - zeyu
tags: ["osre25"]
categories: []
date: 2025-09-28
lastmod: 2025-09-28
featured: true
draft: false
---

Hello! I’m Zeyu Zou! I have been contributing to the **RAG-ST: Retrieval-Augmented Generation for Spatial Transcriptomics** project under the mentorship of Ziheng Duan. My project focuses on developing a framework that predicts spatial gene expression from histology images by combining vision encoders with single-cell RNA-seq references. The goal is to make spatial transcriptomics more affordable, interpretable, and scalable for the research community.

## Introduction  
RAG-ST is designed to reduce the cost and complexity of spatial transcriptomics by leveraging existing histology images and scRNA-seq priors. This work integrates computer vision with retrieval-augmented generation to improve prediction accuracy and interpretability.  

## Methods  
The project used a two-stage pipeline:  
1. **Vision encoder** (ResNet50/ViT) to map histology patches to cell type distributions.  
2. **Retrieval-augmented generation** guided by scRNA-seq profiles to predict gene expression.  

Datasets included **HEST-1K** (paired histology and expression) and **CellxGene Census** as the reference database. Training and evaluation pipelines were implemented in PyTorch.  

## Results  
- Implemented a complete pipeline from histology preprocessing to expression prediction.  
- Achieved higher correlation scores (Pearson/Spearman) and lower errors (MSE/MAE) compared to baseline models.  
- Produced spatial gene expression maps with interpretable retrieval traces and attention weights.  
- Released open-source code, preprocessing scripts, and analysis notebooks for reproducibility.  

## Future Work  
- Extend experiments to additional tissues (lung, liver, tumor samples).  
- Test cross-dataset generalization and robustness.  
- Explore integration into clinical pathology workflows for affordable spatial inference.  

## Acknowledgments  
Thanks to my mentor Ziheng Duan, the UC OSPO team, the HEST-1K dataset contributors, and the CellxGene Census project. This work was conducted under OSRE 2025.  

## Links  
- Repository: [https://github.com/ZeyuZou/rag-st](https://github.com/ZeyuZou/rag-st)  
- Preprint: *RAG-ST: Retrieval-Augmented Generation for Spatial Transcriptomics* (bioRxiv, 2025)  
