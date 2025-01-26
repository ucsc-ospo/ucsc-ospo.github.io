---
title: "Halfway Blog: FSA: Benchmarking Fail-Slow Algorithms"
subtitle: "exploring advanced ML in the RAID slowdown condition analysis"
summary: ""
authors:
 - xikangsong
tags: ["osre24", reproducibility, "machine learning", "storage"]
categories: []
date: 2024-07-23
lastmod: 2024-07-23
featured: false
draft: false

# Featured image

# To use, add an image named `featured.jpg/png` to your page's folder.

# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.

image:
caption: ""
focal_point: ""
preview_only: false
---


## Introduction

Hi, I'm {{%mention xikangsong%}}, a 2024 SoR contributor to the project, working with mentors {{%mention ruidanli%}} and {{%mention kexin-pei%}}. Our FSA-Benchmark project is dedicated to exploring and benchmarking various machine learning models to identify disks at high risk of fail-slow anomalies. We will benchmark a range of machine learning algorithms, from traditional to advanced methods, and compare the results using a comprehensive evaluation system. This will provide a clear view of how machine learning impacts critical error detection in RAID systems.

## Motivation
Fail-slow issues in storage systems , where a disk operates at a significantly reduced speed without completely failing, are subtle and can manifest as consistently higher latency compared to peer disks or recurrent abnormal latency spikes. These issues are challenging to detect but can significantly degrade overall system performance over time. Fixed thresholds are ineffective because latency distributions vary across different clusters, leading to thresholds that are either too low or too high, resulting in numerous false alerts. Therefore, we are enthusiastic about using machine learning models to analyze disk performance data. Machine learning algorithms can deeply learn the trends in the data, providing better detection capabilities.

## Current Progress and Challenges

### Algorithm Implementation:

- **Cost-Sensitive Ranking Model**: Inspired by the paper "Improving Service Availability of Cloud Systems by Predicting Disk Error" presented at the USENIX ATC '18 conference, this model ranks disks based on fail-slow risk.

- **Multi-Prediction Models**: Drawing from "Improving Storage System Reliability with Proactive Error Prediction" presented at the USENIX ATC '17 conference, this approach uses multiple traditional machine learning models to evaluate disk health using diverse features. Various models were tested, with the Random Forest classifier proving most effective.

- **LSTM Model**: This model employs Long Short-Term Memory (LSTM) networks, trained on the first day's data for each cluster and evaluated on data spanning all days. It captures temporal dependencies to accurately predict fail-slow anomalies over time.

### Comprehensive Evaluation:

1. Collected outputs from all algorithms on Chameleon for Perseus data A to Y (25 clusters).
2. Parsed the outputs through a comprehensive evaluation system, recording the true/false positives/negatives.
3. Plotted heat maps to show precision and recall with different look-back days and alert threshold settings.
4. Compared the performance across different clusters to draw conclusions.

### Packaging Code:

- Packaged all the code into a Trovi Jupyter notebook, including the Chameleon server setup, to provide clear steps for running the code and reproducing the experiments. All algorithm testing and result parsing can be easily done here.

### Challenges

Initially, I was unsure how to evaluate the performance of different algorithms. {{%mention ruidanli%}} provided comprehensive guidance on collecting all the results uniformly and parsing them to gather true/false positives/negatives. This approach enabled us to derive meaningful metrics and plot heatmaps for precision and recall. I learned the scientific method of benchmarking performance, and I am grateful for the guidance.

## Future Steps

### Further Investigation of Advanced Algorithms

We plan to explore advanced algorithms such as PatchTST. This will involve systematically collecting outputs and conducting comprehensive benchmarking to assess their performance in identifying fail-slow anomalies.

### Transition to Large Language Models (LLMs)

Recognizing the limitations of traditional machine learning methods, we intend to transition to utilizing Large Language Models (LLMs). LLMs have demonstrated superior capabilities in understanding complex patterns and making accurate predictions. We anticipate that incorporating LLMs into our analysis will enhance our ability to detect and predict fail-slow anomalies more accurately, leading to better overall system reliability.
