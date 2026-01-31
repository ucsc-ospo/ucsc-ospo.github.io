---
title: "AI Data Readiness Inspector (AIDRIN)"
authors: [jeanlucabez, surenbyna]
author_notes: ["Lawrence Berkeley National Laboratory", "The Ohio State University (OSU)"]
tags: ["osre26", "uc", "LBNL", "data science", "AI"]
date: 2026-01-30T10:15:00-07:00
lastmod: 2026-01-30T10:15:00-07:00
---

Garbage In, Garbage Out (GIGO) is a widely accepted quote in computer science across various domains, including Artificial Intelligence (AI). As data is the fuel for AI, models trained on low-quality, biased data are often ineffective. Computer scientists who use AI invest considerable time and effort in preparing the data for AI. 

[AIDRIN](https://arxiv.org/pdf/2406.19256) (AI Data Readiness INspector) is a framework that provides a quantifiable assessment of data readiness for AI processes, covering a broad range of dimensions from the literature. AIDRIN uses metrics from traditional data quality assessment, such as completeness, outliers, and duplicates, to evaluate data. Furthermore, AIDRIN uses metrics specific to assessing AI data, such as feature importance, feature correlations, class imbalance, fairness, privacy, and compliance with the FAIR (Findability, Accessibility, Interoperability, and Reusability) principles. AIDRIN provides visualizations and reports to assist data scientists in further investigating data readiness.

### AIDRIN Multiple File Formats

The proposed work will include improvements in the AIDRIN framework to (1) add support for new file formats such as Zarr, ROOT, and HDF5; and (2) to allow providing custom data ingestion mechanisms.

- **Topics:** `data readiness`, `AI`, `data analysis`
- **Skills:** Python, C/C++, data analysis, good communicator
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** {{% mention jeanlucabez %}} and {{% mention surenbyna %}}