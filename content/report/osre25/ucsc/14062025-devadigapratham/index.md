---
title: "Building a Billion-Scale Vector Embeddings Dataset"
subtitle: "For Real-World ANN Benchmarking and RAG Research"
summary: This post outlines my Google Summer of Code 2025 project with OSRE, focused on building the first open-source billion-scale vector embedding dataset for benchmarking Approximate Nearest Neighbor algorithms.
authors: 
  - prathamesh-devadiga
tags: ["osre25", "gsoc", "vector-embeddings", "rag", "benchmarking"]
categories: []
date: 2025-06-15
lastmod: 2025-06-15
featured: true
draft: false

image:
  caption: "1B Wikipedia Paragraph Embeddings using Open Models"
  focal_point: "Smart"
  preview_only: false
---

As part of the [Billion-Scale Embeddings Dataset project](/project/osre25/OSRE/embeddings), my [proposal](./GSoC-proposal.pdf) under the mentorship of **Jayjeet Chakraborty** aims to create the first large-scale, real-world vector embeddings dataset—bridging the critical gap in Approximate Nearest Neighbor (ANN) benchmarks and Retrieval-Augmented Generation (RAG) systems.

## Motivation

Existing ANN benchmarks often fall short—they’re either synthetic (like SIFT) or too small-scale (≤1M vectors). With the rapid evolution of LLM-based vector search systems (e.g., OpenAI’s 3072d `text-embedding-3-large`), there's a growing need for:

- High-dimensional (>1000d), large-scale (>100M) embeddings
- Real-world distributions (Wikipedia-scale text)
- Open, reproducible benchmarks for the community

## Project Goals

- Generate **1 billion** embeddings from English Wikipedia using open-source models.
- Create multiple dimensional variants: **1024d**, **4096d**, and **8192d**.
- Deduplicate, compress, and store embeddings with rich metadata (URL, timestamps, models).
- Benchmark ANN performance on FAISS, HNSW, and Annoy.
- Distribute the dataset via HuggingFace & AWS S3 with shard-level access.

## Open Source Impact

- **ANN Libraries**: Enable reproducible benchmarking for real-world workloads.
- **RAG Systems**: Evaluate and optimize retrieval at scale using real Wikipedia text.
- **Researchers**: Conduct large-scale studies on dimensionality, ANN accuracy, and compression trade-offs.

---

## About Me

Hi, I'm **Prathamesh Devadiga**, currently pursuing my B.Tech in Computer Science at PES University, Bangalore (2022–2026). My core interests lie in Machine Learning, Deep Learning, Generative AI, and large-scale systems.

### Relevant Experience

- **Founder, Adhāra AI Labs** — leading research in GenAI and RAG systems.  
- **AI Engineer Intern, IndhicAI** — building end-to-end GenAI pipelines.  
- **Research Intern, IIT Indore** — built KASPER, a robust DL malware detector.  
- **Intern, Microsoft Innovation Lab** — built a Mistral 7B-based code review multi-agent system (CodeBLEU: 80).


### Tools I Use

Python, Go, PyTorch, HuggingFace, Spark, vLLM, LangChain, LlamaIndex, AWS, Docker, Kubernetes, Lance, DataSketch, and more.

See more at: [Portfolio](https://prathamesh-portfolio.com) and Connect with here on: [Linkedin](https://www.linkedin.com/in/prathamesh-devadiga/)

---

Thanks to Google Summer of Code and OSRE for supporting this initiative toward better open science!

