---
title: "Enhancing Reproducibility in RAG Frameworks for Scientific Workflows"
subtitle:
summary: "This project addresses the critical issue of non-determinism in Retrieval-Augmented Generation (RAG) systems. We aim to develop a suite of tools, benchmarks, and best practices to ensure scientific workflows using Large Language Models are reliable, transparent, and reproducible."
authors:
  - wbq-321
tags: ["osre25", "reproducibility", "rag", "llm", "ai-for-science"]
categories: ["Project"]
date: 2025-06-25
lastmod: 2025-06-25
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "Smart"
  preview_only: false
---

Hello, I'm Baiqiang. As part of the [Enhancing Reproducibility in RAG Frameworks for Scientific Workflows](https://ucsc-ospo.github.io/project/osre25/pnnl/llm_rag_reproducibility/) project, I am excited to introduce my work on a crucial challenge in modern computational science. My [proposal](https://www.overleaf.com/read/fcbxtpngdnhw#8cc2c8) under the mentorship of Luanzheng "Lenny" Guo at Pacific Northwest National Laboratory and Dongfang Zhao at the University of Washington aims to enhance the reproducibility of AI-driven scientific workflows.

### The Problem: A Crisis of Confidence in AI for Science

Large Language Models (LLMs) are transforming scientific research, from accelerating literature reviews to generating novel hypotheses. However, their power is matched by their pitfalls: a tendency to "hallucinate" facts and a lack of transparency. Retrieval-Augmented Generation (RAG) was developed as a powerful solution, grounding LLM outputs in factual evidence retrieved from a specific knowledge base (like a database of scientific papers).

But a hidden problem lurks within RAG: **non-determinism**. The very first step of a RAG system—the similarity search that finds relevant documents—can produce different results even when asked the same question. Variations in indexing algorithms, data updates, or even the underlying software can change which documents are retrieved. For science, this is a critical flaw. If an experiment cannot be repeated with the same results, its conclusions cannot be trusted. This project tackles that challenge head-on.

### Our Mission: Forging a Path to Reproducible RAG

This project proposes a comprehensive solution to systematically identify, measure, and mitigate non-determinism in RAG frameworks. Our goal is to empower researchers to build and use AI tools with confidence.

Our approach is built on four key pillars:

1.  **Systematic Analysis:** We will conduct a deep dive into popular RAG components (like FAISS, ScaNN, and HNSW) to pinpoint the exact sources of randomness and variability.
2.  **Rigorous Benchmarking:** We will develop a public, open-source benchmarking suite using standardized scientific datasets (from PubMed, arXiv, etc.). This will allow anyone to quantitatively measure the reproducibility of their own RAG pipeline using clear metrics like retrieval overlap and rank correlation.
3.  **Targeted Enhancements:** Based on our findings, we will implement practical solutions, including:
    *   Promoting deterministic algorithms and configurations.
    *   Building robust data versioning and provenance tracking tools (inspired by DVC and Git LFS).
    *   Creating tools for precise configuration management to capture the entire experimental setup.
4.  **Practical Guidance and Open Source Tools:** We will distill our insights into comprehensive documentation, reusable code examples, and best practices. All tools and findings will be contributed back to the open-source community.