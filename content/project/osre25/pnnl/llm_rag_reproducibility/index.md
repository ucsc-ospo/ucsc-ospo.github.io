---
title: "Enhancing Reproducibility in RAG Frameworks for Scientific Workflows"
authors: [kakulo]
author_notes: ["Computer Scientist, Pacific Northwest National Laboratory"]
tags: ["reproducibility", "LLM", "RAG", "AI", "PNNL"]
date: 2025-02-20T09:00:00-07:00
lastmod: 2025-02-20T09:00:00-07:00
---

Retrieval-Augmented Generation (RAG) frameworks, which merge the capabilities of retrieval systems and generative models, significantly enhance the relevance and accuracy of responses produced by large language models (LLMs). These frameworks retrieve relevant documents from a large corpus and use these documents to inform the generative process, thereby improving the contextuality and precision of the generated content. Ensuring reproducibility in data queries using similarity search within these RAG frameworks is critical for maintaining the reliability and consistency of scientific workflows. Reproducibility ensures that the same input query consistently yields the same output, which is vital for scientific tasks that rely on precise and repeatable results. Inconsistencies can arise from various sources, affecting the trustworthiness of scientific outcomes. Differences in retrieval algorithms can lead to variable sets of documents being retrieved for the same query. Variations in data indexing methods can cause inconsistencies in how documents are ranked and accessed. The stochastic nature of LLM operations introduces an element of randomness in the generative process. Updates in datasets can also alter the baseline against which queries are processed and interpreted, leading to different results over time. 

This proposal aims to address these reproducibility challenges in similarity searches within RAG frameworks. This work involves analyzing the root causes of non-determinism, benchmarking and validating the consistency of query results, implementing enhancements to minimize variability, and developing tools and best practices to ensure reproducibility. Reproducibility in data queries can be influenced by several factors, including updates in datasets, differences in retrieval algorithms, varying data indexing methods, and the stochastic nature of LLM operations. Each of these factors can cause variability in the documents retrieved and in the generated responses. Ensuring consistency in query results across different runs is crucial for maintaining the integrity of LLM-driven scientific research, allowing researchers to confidently build upon prior work and achieve reliable, trustworthy outcomes.

### Workplan

The proposed work will include: (1) Identifying sources of non-determinism and variability, such as algorithmic differences and indexing methods, in RAG; (2) Utilizing standardized scientific datasets to benchmark the reproducibility of similarity search results across different RAG frameworks; (3) Establishing protocols for handling dataset updates to ensure that such changes do not impact the reproducibility of similarity search results; and (4) Implementing mechanisms to track and document updates to datasets, ensuring that changes are reflected consistently across all instances of the RAG framework. By addressing these areas, the proposed work aims to mitigate challenges related to reproducibility in similarity search queries within RAG frameworks, ultimately enhancing the reliability and trustworthiness of scientific research outcomes.

- **Topics:** `Reproducibility` `LLM` `RAG` `Scientific Workflows`
- **Skills:** C/C++, Python
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** {{% mention kakulo %}}
