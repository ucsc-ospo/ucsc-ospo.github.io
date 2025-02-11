---
title: "Kolmogorov-Arnold-based Transformer for LLMs: Implementation, Evaluation and Benchmarking "
authors: [saisumanv, zahmeeth]
author_notes: ["PhD Candidate, University of Nebraska-Lincoln","Assistant Professor, West Virginia University"]
tags: ["osre25", "KALLM", "Transformers", "Kolmogorov-Arnold Networks", "smollm2]
date: 2025-02-09T10:15:56-07:00
lastmod: 2025-02-09T10:15:56-07:00
---

###  Project Description
<!--- KALLM introduction --->
<!--- importance --->
[KALLM](https://github/saisumanv/KALLM) project proposes a new Kolmogorov-Arnold Network (KAN)-based Transformer implementation of an open-source LLM called SmolLM2. Transformers have found increasing success in many open-source LLMs across language reasoning tasks like text generation, summarization and some tasks imitating advanced critical thinking. However, Kolmogorov-Arnold Networks (KANs) are an attractive alternative to the Multi-Layer Perceptrons (MLPs) which are used in these Transformer architectures by default. KAN-based Transformers (KATs) offer several advantages over MLPs. (i) They follow the universal approximation property and hence can theoretically approximate any function i.e. they can learn from any complex input patterns. (ii) They are more interpretable as they decompose the entire input into multiple manageable components with each layer processing one component. This is unlike MLPs, where each layer processes the input sequences holistically. (iii) KANs can lead to faster convergence on certain reasoning tasks due to their ability to break down the input sequences into simple univariate functions. 

However, currently there exist little to no open-source implementations of KAN-based Transformers in open-source LLMs. Until recently, an efficient implementation of KAN was not available; the same can be said for KAN-based Transformer implementations. With the recent efficient implementations of open-source KAN-based Transformers (KATs), integrating them into open-source LLM engines becomes a possibility.  This project will implement KAT as the core architecture of the Transformer in SmolLM2, an open-source LLM and perform evaluation and benchmarking against language reasoning tasks. 

### Project Objectives


### Project Methodology


### Project Benchmark Suites

### Project Benchmark Testbeds


### Project Deliverables



### PyLops-MPI

- **Topics**: Towards High Performance NCCL-enabled 2D partitioned PyLops-MPI library
- **Skills**: Python proficiency, scikit-learn, Experience with Linux, Introductory Experience with Cloud Computing Platoforms
- **Difficulty**: Easy-Medium
- **Size**: Easy-Medium (175 hours)
- **Mentor**: {{% mention saisumanv %}}, {{% mention zahmeeth %}}
