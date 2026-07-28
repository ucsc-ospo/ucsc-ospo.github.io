---
title: "Hello from OSRE 2026: CellQuery-ST"
subtitle: "Cell-Aware Query Grounding for Single-Cell and Neighborhood Retrieval from Histology"
summary: ""
authors:
  - twu0955
tags: ["osre26"]
categories: []
date: 2026-06-19
lastmod: 2026-06-19
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hi everyone! My name is Tong Wu, and I'm excited to be part of the OSRE 2026 cohort. I'm a master's student at the University of Melbourne, with a strong interest in machine learning and its applications to biology and medicine. This summer I'll be working on **CellQuery-ST** under the mentorship of Xi Li.

CellQuery-ST tackles a gap in computational pathology. Today's models can predict gene expression or answer broad, slide-level questions, but they can't yet answer *cell-aware* questions about a histology image — things like "Where are the B-cell follicles?", "Which regions show inflammatory myeloid activity?", or "Which neighborhoods resemble a vascular niche?" My goal is to make this kind of biologically grounded querying possible on new slides.

To do this, I'll build a cell-aware query grounding framework that learns from spatial omics data during training but only needs the image itself at inference time. Each slide is preprocessed into a spatial index of cells, patches, and neighborhoods, and a natural-language query is matched against that index to retrieve or score the relevant spatial evidence. The system pairs spatial pathology data with CellNet — an existing paired single-cell and language resource — to connect text queries with cell identities, cell states, and higher-level biological concepts.

The main deliverables will be:

1. A benchmark covering four task families: cell-type grounding, cell-state/programme grounding, spatial-niche grounding, and communication-hotspot grounding.
2. A reusable slide indexing and retrieval pipeline for histology images.
3. Reproducible baseline models and evaluation utilities for seen/unseen query generalization.
4. Documentation and tutorial notebooks showing how to preprocess a new slide, run queries, and evaluate results.

I'll be sharing updates here throughout the summer — thanks for following along!

- Proposal: [Google Drive](https://drive.google.com/file/d/1jb7ivJ55eLHjErivt21yn9ybWNZPboNf/view?usp=sharing)
