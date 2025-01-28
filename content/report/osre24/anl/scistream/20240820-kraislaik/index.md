---
title: "Final Blog: FSA - Benchmarking Fail-Slow Algorithms"
subtitle: "Exploring Advanced ML in RAID Slowdown Condition Analysis"
summary: ""
authors: [kexin-pei, ruidanli, xikangsong]
tags: ["osre24", reproducibility, "machine learning", "storage"]
categories: []
date: 2024-08-14
lastmod: 2024-08-14
featured: false
draft: false

image:
caption: ""
focal_point: ""
preview_only: false
---

## Introduction

Hello! I hope you're enjoying the summer as much as I am. I'm excited to join the SOR community as a 2024 contributor. My name is {{%mention xikangsong%}}, and I'm thrilled to collaborate with mentors {{%mention ruidanli%}} and {{%mention kexin-pei%}} on the FSA-Benchmark project. This project is dedicated to exploring and benchmarking various machine learning models to identify disks at high risk of fail-slow anomalies. Throughout this journey, we tested a broad range of algorithms, from traditional approaches to state-of-the-art techniques, using a robust evaluation system to compare their effectiveness.

In the first half of the project, I focused on implementing and testing different machine learning models for detecting disks at high risk of fail-slow anomalies. This involved setting up initial models such as the Cost-Sensitive Ranking Model and Multi-Prediction Models, and beginning to explore LSTM networks for analyzing input disk data.

In the second half, I built upon this foundation by refining the evaluation processes, exploring advanced models like PatchTST, and investigating the potential of large language models (LLMs) for detecting subtle fail-slow conditions in storage systems. This blog post will summarize the key achievements, findings, and comparisons with baseline models from this phase.

## Key Achievements

1. **Comprehensive Benchmarking and Evaluation:**
   - I extended the benchmarking framework to evaluate multiple algorithms across 25 different data clusters on PERSEUS. This process involved generating and analyzing heatmaps that visualized the precision and recall of each model under various settings, providing a clear understanding of each approach's strengths and limitations.

2. **Exploration of Advanced Machine Learning Models:**
   - **LSTM Model:** I implemented the Long Short-Term Memory (LSTM) model, specifically designed for sequential data, to capture temporal dependencies in disk performance metrics. This model was used to predict potential fail-slow anomalies by analyzing historical data. Using Mean Squared Error (MSE) as a risk indicator, the LSTM model outperformed baseline approaches like the Cost-Sensitive Ranking Model and Multi-Prediction Models, especially in clusters where latency patterns between faulty and normal disks were distinct, such as in Cluster_P. This resulted in a higher precision and fewer false positives. However, in clusters with more complex and overlapping data distributions, like Cluster_L, the LSTM model's performance diminished, similar to that of the baseline models

   - **PatchTST Model:** I also introduced and evaluated the PatchTST model, which is built on a transformer-based architecture known for its ability to handle sequential data by capturing long-range dependencies and intricate temporal patterns. Unlike traditional models, PatchTST processes time series data in segments or "patches," enhancing its ability to predict disk behavior over extended periods. Like the LSTM model, PatchTST uses outlier MSE values to assess disk risk. In clusters with a clear separation between faulty and normal disks, PatchTST outperformed baseline models by effectively identifying faulty patterns. However, similar to the LSTM model, PatchTST encountered difficulties in clusters with significant data overlap, such as Cluster_L.

3. **Investigation into Large Language Models (LLMs):**
   - I explored the use of GPT-4-o-mini for fail-slow detection. While large language models (LLMs) showed potential, particularly in reducing false positives and improving precision over baseline models, they did not consistently outperform specialized models like LSTM and PatchTST in this context. LLMs struggled with recall, especially as thresholds increased, revealing the challenges of adapting LLMs to time series data. This limitation arises because LLMs are primarily trained for natural language generation tasks, not for analyzing time series data. As a result, their ability to fully capture anomalies is limited. To improve their effectiveness, we need to develop methods that help LLMs better understand time series data. For example, incorporating statistical information about each disk’s performance could enhance LLMs' understanding, leading to better precision in fail-slow detection.
 
## Conclusion and Future Work

The work in this project demonstrated that while advanced machine learning models like LSTM and PatchTST offer significant potential for detecting fail-slow conditions, challenges remain in ensuring consistent performance across diverse clusters. Compared to baseline models, these advanced approaches generally provided better precision and recall, especially in clusters with distinct data patterns between faulty and normal disk performance time series. However, the persistent difficulties in more complex clusters indicate the need for further refinement.

Moving forward, future work will focus on refining these models, particularly in improving their performance in challenging clusters like Cluster_L. Additionally, I plan to further explore techniques such as prompt engineering for LLMs to better tailor them for time series analysis and fail-slow detection tasks.

## Deliverables

- **Repository:** All comprehensive analysis code and source code can be found in the [FSA_BENCHMARK GitHub Repository](https://github.com/songxikang/FSA_BENCHMARK).
- **Jupyter Notebook:** A notebook to reproduce the experiments and benchmarks on Chameleon: [Chameleon Experiment Notebook](https://chameleoncloud.org/experiment/share/585c1fc0-924c-4501-b143-ad6476339aa8).
- **Final Report:** Comprehensive algorithm performance evaluation for all methods in [FSA-Benchmarking Final Report](https://docs.google.com/document/d/1NONl23sXK-qE4Krx3JwG7gCrNiNmaaW1t4WVzMmomLQ/edit?usp=sharing).
