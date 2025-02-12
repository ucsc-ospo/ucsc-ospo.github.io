---
title: "AI Data Readiness Inspector (AIDRIN)"
authors: [jeanlucabez, "Suren Byna"]
author_notes: ["Research Scientist, Lawrence Berkeley Lab", " The Ohio State University (OSU)"]
tags: ["osre25", "uc", "LBNL", "data science", "AI"]
date: 2025-02-11T10:15:00-07:00
lastmod: 2025-02-11T10:15:00-07:00
---

Garbage In Garbage Out (GIGO) is a universally agreed quote by computer scientists from various domains, including Artificial Intelligence (AI). As data is the fuel for AI, models trained on low-quality, biased data are often ineffective. Computer scientists who use AI invest considerable time and effort in preparing the data for AI. 

[AIDRIN](https://arxiv.org/pdf/2406.19256) (AI Data Readiness INspector) is a framework that provides a quantifiable assessment of the readiness of data for AI processes, covering a broad range of readiness dimensions available in the literature. AIDRIN uses metrics in traditional data quality assessment, such as completeness, outliers, and duplicates, for data evaluation. Furthermore, AIDRIN uses metrics specific to assess data for AI, such as feature importance, feature correlations, class imbalance, fairness, privacy, and FAIR (Findability, Accessibility, Interoperability, and Reusability) principle compliance. AIDRIN provides visualizations and reports to assist data scientists in further investigating the readiness of data.

### AIDRIN Visualizations and Science Gateway

The proposed work will include improvements in the AIDRIN framework to (1) enhance, extend, and optimize the visualizations of metrics related to all six pillars of AI data readiness and (2) set up a science gateway on NERSC or AWS cloud service.

- **Topics:** `data readiness` `AI`
- **Skills:** Python, C/C++, good communicator
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** {{% mention jeanlucabez %}} and [Suren Byna](mailto:sbyna@lbl.gov)