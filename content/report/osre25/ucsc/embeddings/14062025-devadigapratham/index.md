---
title: "Building a Billion-Scale Vector Embeddings Dataset"
subtitle: "For Real-World ANN Benchmarking and RAG Research"
summary: This post outlines my Google Summer of Code 2025 project with OSRE, focused on building the first open-source billion-scale vector embedding dataset for benchmarking Approximate Nearest Neighbor algorithms.
authors: 
  - devadigapratham
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

# Billion Vector Embeddings Dataset

As part of the [Billion-Scale Embeddings Dataset project](/project/osre25/ucsc/embeddings), my [proposal](GSoC-proposal.pdf) under the mentorship of **Jayjeet Chakraborty** aims to create the first large-scale, real-world vector embeddings dataset—bridging the critical gap in Approximate Nearest Neighbor (ANN) benchmarks and Retrieval-Augmented Generation (RAG) systems.

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


