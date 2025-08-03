---
title: "Midway Through GSoC"
subtitle: "Building a Billion-Scale Code Embeddings Dataset"
summary: A midterm update on my GSoC 2025 project under OSRE. This post covers the motivation, goals, and current progress on creating a real-world code embeddings dataset for ANN and RAG applications.
authors: 
  - devadigapratham
tags: ["osre25", "gsoc", "vector-embeddings", "code", "benchmarking", "rag"]
date: 2025-07-14
lastmod: 2025-07-14
featured: true
draft: false
---

# Midway Through GSoC

Hello everyone! I’m Pratham Devadiga, and I’m thrilled to share a midterm progress update on my [GSoC 2025 project](https://summerofcode.withgoogle.com/programs/2025/projects/GcstSGAO) with the Open Source Research Experience (OSRE). My project is focused on building the **first open-source billion-scale vector embeddings dataset** from **real-world open source code** to support benchmarking of Approximate Nearest Neighbor (ANN) algorithms and facilitate research in Retrieval-Augmented Generation (RAG).

## Project Overview

The goal of this project is to address a critical gap in the ecosystem: existing ANN benchmarks are either synthetic or limited in scale. With the explosion of code-focused LLMs and embedding models, there's a pressing need for:

- **High-volume, high-dimensional vector datasets** built from real-world data (open-source codebases).
- **Open, reproducible benchmarks** that reflect realistic RAG workloads.
- A dataset that can be used to evaluate **ANN libraries** like FAISS, HNSW, and Annoy on massive and practical retrieval tasks.

Our approach is to use high-quality open-source code repositories to extract meaningful code chunks, encode them into vector embeddings using open models, and make these datasets publicly available with metadata for downstream benchmarking and analysis.

## Progress So Far

We’ve made substantial foundational progress in the first half of the coding period. Key highlights:

- **Tested multiple embedding models** such as `codeBERT`, `MiniLM-L6-v2`, and `all-mpnet-base-v2`, evaluating trade-offs in speed, dimensionality, and GPU memory.
- **Selected `codebert-base`** (768d) as the current model for phase one due to its stable performance and manageable resource footprint.
- Implemented and validated a complete **script pipeline** to:
  - Traverse large open-source repositories.
  - Extract and chunk code intelligently (functions, classes, modules).
  - Encode code into embeddings and attach metadata (repo, file path, license).
  - Store results efficiently in parquet and NumPy formats.
- **Tested all components** of the pipeline on sample datasets using multi-GPU setups, ensuring compatibility and robustness.

## Challenges and Learnings

Building a billion-scale dataset from real-world codebases is no small task. Here's what we’ve encountered and learned along the way:

### 1. Multi-GPU Pipeline Design
Naively parallelizing the embedding process caused memory overflow and deadlocks due to model reloading across processes. We refactored the code using `torch.multiprocessing` and pinned GPU contexts to avoid such issues, improving throughput on multi-GPU machines.

### 2. Embedding Trade-offs
We experimented with larger models but found that their generation time and memory use were too high to be practical in early phases. This helped us narrow down to scalable configurations for initial dataset generation.

### 3. Preparing for Scale
Although the embeddings are not generated yet, all scripts are now **modular, parallelized, and reproducible**, ensuring a smooth transition to billion-scale data generation in the second half.

## What’s Next

The second half of the project will focus on:

- **Scaling up embedding generation** to >1B code chunks across hundreds of open-source repositories.
- **Running benchmarks** using FAISS, HNSW, and Annoy on these embeddings.
- **Releasing the dataset** on Hugging Face and AWS S3 with sharded access and metadata.
- **Writing a detailed benchmarking report** comparing speed, accuracy, and memory trade-offs across ANN algorithms.

## Final Thoughts

This journey so far has taught me a lot about building large-scale ML pipelines, managing real-world compute constraints, and ensuring reproducibility for research-grade datasets. I'm grateful to my mentor **Jayjeet Chakraborty** and the OSRE team for their continuous support and guidance.

Excited for the next half, where the real scale begins!

Stay tuned for updates. You can find more about the project on my [OSRE project page](/project/osre25/ucsc/embeddings).
