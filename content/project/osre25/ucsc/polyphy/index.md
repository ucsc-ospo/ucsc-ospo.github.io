---
title: "Mediglot"
authors: [oelek, kirandeol]
tags: ["osre25", "uc", "data science", "scientific visualization"]
date: 2025-02-04
lastmod: 2024-02-05
---

[PolyPhy](https://github.com/PolyPhyHub/PolyPhy) is a GPU-oriented agent-based system for reconstructing and visualizing *optimal transport networks* defined over sparse data. Rooted in astronomy and inspired by nature, we have used an early prototype called [Polyphorm](https://github.com/CreativeCodingLab/Polyphorm) to reconstruct the [Cosmic web](https://youtu.be/5ILwq5OFuwY) structure, but also to discover network-like patterns in natural language data. You can see an instructive overview of PolyPhy in our [workshop](https://elek.pub/workshop_cross2022.html) and more details about our research [here](https://elek.pub/projects/Rhizome-Cosmology). Recent projects, such as [Polyglot](https://github.com/PolyPhyHub/PolyGlot) and [Mediglot](https://github.com/Ayush-Sharma410/MediGlot) have focused on using PolyPhy to better visualize language embeddings.

### Medicinal Language Embeddings

- **Topics:** `Large Language Models` `NLP` `Embeddings` `Medicine`
- **Skills:** Python, JavaScript, Data Science, Technical Communication
- **Difficulty:** Challenging
- **Size:** Large (350 hours)
- **Mentors:** {{% mention oelek %}}, [Kiran Deol](mailto:kdeol@ualberta.ca)

This project aims to refine and enhance Mediglot, a web application for visualizing 3D medicinal embeddings, which extends the Polyglot app and leverages the PolyPhy toolkit for network-inspired data science. Mediglot currently enables users to explore high-dimensional vector representations of medicines (derived from their salt compositions) in a 3D space using UMAP, as well as analyze similarity through the innovative Monte-Carlo Physarum Machine (MCPM) metric. Unlike traditional language data, medicinal embeddings do not have an inherent sequential structure. Instead, we must work with the salt compositions of each medicine to create embeddings that are faithful to the intended purpose of each medicine. 

This year, we would like to focus on exploring and integrating state-of-the-art AI techniques and algorithms to improve Mediglot's clustering capabilities and its representation of medicinal data in 3D. The contributor will experiment with advanced large language models (LLMs) and cutting-edge AI methods to develop innovative approaches for refining clustering and extracting deeper insights from medicinal embeddings. Beyond LLMs, we would like to experiment with more traditional language processing methods to design novel embedding procedures. Additionally, we would like to experiment with other similarity metrics. While the similarity of two medicines depends on the initial embedding, we would like to examine the effects of different metrics on the kinds of insights a user can extract. Finally, the contributor is expected to evaluate and compare different algorithms for dimensionality reduction to enhance the faithfulness of the visualization and its interpretability.

The ideal contributor for this project has experience with Python (and common scientific toolkits such as NumPy, Pandas, SciPy). They will also need some experience with JavaScript and web development (MediGlot is distributed as a vanilla JS web app). Knowledge of embedding techniques for language processing is highly recommended.

**Specific tasks:**
- Closely work with the mentors to understand the context of the project and its detailed requirements in preparation for the proposal.
- Become acquainted with the tooling (PolyPhy, PolyGlot, Mediglot) prior to the start of the project period.
- Explore different embedding techniques for medicinal data (including implementing novel embedding procedures).
- Explore different dimensionality reduction techniques, with a focus on faithful visualizations.
- Document the process and resulting findings in a publicly available report.
