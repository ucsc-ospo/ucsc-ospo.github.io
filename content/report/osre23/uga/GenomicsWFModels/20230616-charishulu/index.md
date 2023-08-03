---
title: "Reproducible Analysis & Models for Predicting Genomics Workflow Execution Time"
subtitle: ""
summary:
authors: ['charishulu']
tags: ["osre23", reproducibility]
categories: [SoR'23]
date: 2023-06-16
lastmod: 2023-06-16
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

Hi! I'm Charis, an undergraduate student in the IT and Big Data Analytics program at the Calvin Institute of Technology. As part of the [Reproducible Analysis & Models for Predicting Genomics Workflow Execution Time](/project/osre23/uga/GenomicsWFModels) my [proposal](https://drive.google.com/file/d/1dFkC2A0HUVaWd6NpCbTjRZVfYxQ7jRxJ/view?usp=sharing) under the mentorship of {{% mention inkee.kim %}} and **Martin Putra** aims to gain insight into features that are highly correlated with execution times of genomics workflows and build machine learning models for predicting workflow execution time.

Genomics workflows exhibit a long-tail pattern in their execution times. According to the previous project team's findings, approximately 2% of genomics workflows had a median execution time of up to 15%, resulting in weeks of execution. Interestingly, it was observed that input quality plays a role in these execution time differences. Therefore, we will analyze features such as the quality of input data as well as the amount of resources allocated in the execution of genomics workflows to find features that correlate with execution time. Based on these features we will build a machine learning model that can predict the execution time of genomics workflows.

By collaborating with Shayantan Banerjee (another contributor) who will study data quality, I will study the system metrics of genomics workflows both at workflow-level and tool-level. Metrics will be collected by running genomics workflows using the Slurm workload manager under various resource allocation conditions. Genomics workflows will be executed on Chameleon clusters of different sizes.