---
title: "Halfway Through GSoC: My Experience and Progress"
subtitle: "RAG-ST: Retrieval-Augmented Generation for Spatial Transcriptomics"
summary: "An update on my progress building a retrieval-augmented gene expression prediction framework from histology images as part of the OSRE 2025 program."
authors: 
  - zeyuzou
tags: ["osre25"]
categories: []
date: 2025-07-17
lastmod: 2025-07-17
featured: false
draft: false

# Featured image
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

As part of the [RAG-ST](https://ucsc-ospo.github.io/project/osre25/uci/rag-st/) project, my [proposal](https://drive.google.com/file/d/1_yUf1NlVRpBXERCqnOby7pgP4WrWrZsr/view) under the mentorship of **Ziheng Duan** aims to build a **retrieval-augmented generation** framework to predict spatial gene expression from histology images.

---

## 🚀 Achievements

### ✅ Ran the HEST-1K Pipeline  
I successfully ran gene expression prediction models on the **HEST-1K** dataset, reproducing baseline image-to-expression workflows and setting up data loaders, evaluation metrics, and visual inspection of outputs.

### ✅ Explored Tangram’s Alignment Code  
I studied and ran **Tangram**, a well-known scRNA-seq to ST alignment method, gaining key insights into cross-modality mapping. These ideas will inform our strategy to align histology images to scRNA-seq data.

### ✅ Designed the RAG-ST Architecture  
I drafted the architecture for the RAG-ST pipeline, including:
- Vision encoder to process image patches.
- Retrieval module to find relevant examples from a curated database.
- Generation head that conditions predictions on the retrieved examples — allowing transparency and context-aware outputs.

---

## 🧠 Challenges

- **Data Alignment**: Spatial transcriptomics datasets often lack perfect alignment between histology, gene expression, and scRNA-seq, requiring custom preprocessing and normalization.
- **Trade-off Between Interpretability and Accuracy**: Retrieval-augmented designs allow us to trace the origin of predictions but require care to avoid overfitting or performance drops.
- **Computation**: High-resolution images and large-scale retrieval can be computationally expensive. I’ve begun exploring downsampling and vector database indexing strategies.

---

## 🔜 What's Next

- 🔧 Build the **end-to-end retrieval-generation pipeline**
- 🧬 Prototype **histology-to-scRNA-seq** alignment using adapted Tangram ideas
- 📊 Benchmark **RAG-ST vs. MLP baselines**
- 👁️ Develop **interpretability visualizations** to show which samples were retrieved for each prediction

---

## 🧾 Deliverables Progress

| Deliverable                | Status        |
|---------------------------|---------------|
| HEST-1K Baseline Pipeline | ✅ Completed  |
| Tangram Exploration       | ✅ Completed  |
| Data Curation             | 🟡 In Progress |
| RAG-ST Architecture       | ✅ Drafted    |
| Full Pipeline             | ⏳ Planned    |
| Evaluation & Comparison   | ⏳ Planned    |

---

## 🙌 Closing Thoughts

It's been a rewarding first half of GSoC. I’ve gained hands-on experience with spatial transcriptomics datasets, explored state-of-the-art tools like Tangram, and laid the groundwork for a new interpretable gene prediction model.

I’m excited to continue building RAG-ST and look forward to sharing more results soon. Huge thanks to my mentor **Ziheng Duan** for the guidance and support throughout!

If you have questions or want to discuss spatial modeling, feel free to reach out.
