---
title: "Mid-Term Report: Uncovering the True Sources of Non-Reproducibility in AI for Science"
subtitle:
summary: "Mid-project update: Our comprehensive testing framework reveals that the common suspect for RAG non-reproducibility, the FAISS library, is surprisingly deterministic. The true culprits are more subtle: hardware differences and numerical precision. This discovery sharpens our focus on building tools for total environmental control."
authors:
  - wbq-321
tags: ["osre25", "reproducibility", "rag", "llm", "ai-for-science"]
categories: ["Project Update"]
date: 2025-08-01
lastmod: 2025-08-01
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

Hello, I'm Baiqiang. I’m excited to share a mid-term update from the [Enhancing Reproducibility in RAG Frameworks for Scientific Workflows](https://ucsc-ospo.github.io/project/osre25/pnnl/llm_rag_reproducibility/) project. This journey, mentored by Luanzheng "Lenny" Guo and Dongfang Zhao, has taken a fascinating and unexpected turn, leading to a much deeper understanding of what it takes to build truly reliable AI for science.

### The Search for an Invisible Bug

As a quick recap, our project tackles the critical problem of **non-determinism** in Retrieval-Augmented Generation (RAG) systems. For science to be trustworthy, it must be repeatable. If an AI system gives different answers to the same question, it fails this fundamental test. Our initial goal, outlined in my [proposal](https://www.overleaf.com/read/fcbxtpngdnhw#8cc2c8), was to find and fix the sources of this inconsistency, which we believed lay within the retrieval algorithms themselves.

To do this, we built a comprehensive testing framework capable of running thousands of controlled experiments. We designed it to meticulously measure the consistency of retrieval results while varying everything from the indexing algorithm to the underlying hardware.

### A Surprising Discovery: The Usual Suspect is Innocent

The common wisdom in the community is that high-performance, approximate search libraries like FAISS are a major source of randomness. We put this to the test, running repeated queries against various index types, including complex ones like `HNSW` and `IndexIVF`.

Our results were clear and surprising: **FAISS is remarkably reproducible out of the box.** When run on a consistent hardware and software stack, it returns the exact same results, every single time. The library appears to have robust internal seed management that ensures deterministic behavior.

This finding was a pivotal moment. The non-reproducibility that researchers observe in practice is real, but it doesn't come from where we expected. The problem isn't the algorithm itself, but the environment it runs in. Our investigation immediately shifted to find the real culprits.

### Pinpointing the True Sources of Non-Determinism

Our framework quickly helped us identify the true sources of inconsistency:

1.  **Hardware-Induced Variation (CPU vs. GPU):** This is the most significant factor. Running the exact same retrieval code can produce different document rankings and even different document sets when executed on a CPU versus a GPU. This is likely due to subtle differences in floating-point arithmetic and library optimizations in the hardware stack.
2.  **The Impact of Numerical Precision:** We also confirmed that changing the floating-point precision of the data (e.g., from FP32 to FP16) can introduce small numerical variations that are just large enough to reorder the results, potentially changing the evidence the LLM receives.

### Our Mission Refined: Building Tools for Environmental Control

This discovery has sharpened our project's mission. The challenge is not to "fix" a supposedly random algorithm, but to develop the tools and best practices to control for the entire experimental environment. Our focus for the second half of the project is to:

1.  **Develop a Hardware-Aware Configuration Tracker:** We are building a tool that goes beyond logging software versions. It will capture the critical details of the hardware environment—CPU/GPU model, CUDA version, etc.—and link them directly to an experiment's results.
2.  **Create a Cross-Environment Validation Suite:** Our open-source benchmarking suite will empower researchers to test their own pipelines. Crucially, it will help them identify and diagnose inconsistencies when moving workflows between different machines, such as from a local laptop to a cloud-based GPU.
3.  **Establish New Best Practices:** We will distill our findings into clear, actionable guidance. The key recommendation is no longer just about choosing the right algorithm, but ensuring a consistent and well-documented hardware and software environment to guarantee reproducible outcomes.

By following the evidence, we’ve uncovered the root cause of a critical problem in AI-driven research. We are now developing the solutions needed to manage it, paving the way for a future where scientific discoveries powered by AI are built on a foundation of verifiable trust.