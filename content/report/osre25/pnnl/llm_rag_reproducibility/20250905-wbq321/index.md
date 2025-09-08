---
title: "Final Report: A Systematic Investigation into the Reproducibility of RAG Systems"
subtitle:
summary: "Final project report: This project delivered ReproRAG, a comprehensive framework to benchmark reproducibility in Retrieval-Augmented Generation systems. Our large-scale empirical study reveals that core retrieval algorithms like FAISS are perfectly deterministic under controlled conditions, falsifying a common assumption. We identified the true, dominant sources of uncertainty as the choice of embedding model and dynamic data changes, establishing a clear hierarchy of reproducibility challenges."
authors:
  - wbq-321
tags: ["osre25", "reproducibility", "rag", "llm", "ai-for-science", "final-report"]
categories: ["Project Update"]
date: 2025-09-05
lastmod: 2025-09-05
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

I'm Baiqiang, and this is the final report for the [Enhancing Reproducibility in RAG Frameworks for Scientific Workflows](https://ucsc-ospo.github.io/project/osre25/pnnl/llm_rag_reproducibility/) project, mentored by Luanzheng "Lenny" Guo and Dongfang Zhao. This project successfully developed a novel framework to quantitatively measure reproducibility in AI systems, yielding several surprising and impactful results.

### The Challenge: The Need for Systematic Measurement

Retrieval-Augmented Generation (RAG) is a cornerstone of AI for science, but its reliability is often compromised by non-determinism. While this issue was a known concern, a fundamental challenge was the lack of standardized tools and methodologies to systematically measure and quantify the sources of this inconsistency. Without a rigorous way to analyze the problem, it was difficult to move beyond ad-hoc tests and establish the true root causes, hindering the development of truly trustworthy AI systems for science.

### Our Contribution: The ReproRAG Framework

To address this gap, the central contribution of this project is **ReproRAG**, a comprehensive, open-source benchmarking framework. ReproRAG is designed to systematically investigate sources of uncertainty across the entire RAG pipeline by:
*   **Isolating Variables:** It allows for controlled experiments on embedding models, numerical precision, retrieval algorithms, hardware configurations (CPU/GPU), and distributed execution environments.
*   **Quantifying Uncertainty:** It employs a suite of metrics—including Exact Match Rate, Jaccard Similarity, and Kendall's Tau—to precisely measure the impact of each variable on the final retrieved results.

### Key Findings: A New Hierarchy of Uncertainty

Our large-scale empirical study using ReproRAG challenged common assumptions and established a clear hierarchy of what actually impacts reproducibility.

1.  **Core Algorithms Are Not the Problem:** Our most surprising finding is that modern retrieval libraries like FAISS are perfectly reproducible out-of-the-box. Across all tested index types (including approximate ones like HNSW and IVF) and execution environments (single-node CPU/GPU and multi-node distributed systems), we achieved perfect run-to-run reproducibility (1.000 scores on all metrics) when environmental factors like random seeds were controlled. This falsifies the common hypothesis that approximate nearest neighbor algorithms are a primary source of randomness.

2.  **Embedding Model Choice is a Dominant Source of Variation:** We found that the choice of the embedding model is a dominant factor driving result variation. When comparing outputs from different state-of-the-art models (BGE, E5, Qwen) for the same query, the agreement was very low (e.g., Overlap Coefficient of ~0.43-0.54). This means a scientific conclusion drawn with one model may not be reproducible with another, as they are fundamentally "seeing" different evidence.

3.  **Environmental Factors Introduce Measurable "Drift":**
    *   **Numerical Precision:** Changing floating-point precision (e.g., FP32 vs. FP16) was a guaranteed source of variation, but it caused a small and quantifiable "embedding drift" rather than chaotic changes.
    *   **Data Insertion:** Incrementally adding new data to an index caused a predictable "displacement" of old results, not a re-shuffling. The relative ranking of the remaining original documents was perfectly stable (Kendall's Tau of 1.000).

4.  **Common Determinism Flags Can Be Ineffective:** Our tests showed that popular software-level controls, like `cudnn.deterministic` flags in PyTorch, had no observable effect on the output of modern transformer-based embedding models. This underscores the necessity of empirical validation over assuming that framework settings work as advertised.

### Conclusion

This project successfully shifted the focus of the RAG reproducibility problem. The key challenge is not to fix supposedly "random" algorithms, but to rigorously control the entire experimental environment. We delivered **ReproRAG**, a framework that empowers researchers to do just that. Our findings provide actionable insights for the community: efforts to improve reproducibility should focus less on the retrieval algorithms themselves and more on disciplined management of embedding models, data versioning, and numerical precision.