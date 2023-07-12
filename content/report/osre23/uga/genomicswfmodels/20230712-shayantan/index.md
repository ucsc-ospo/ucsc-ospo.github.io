---
title: "Reproducible Analysis & Models for Predicting Genomics Workflow Execution Time"
subtitle: ""
summary: ""
authors: [shayantan]
author_notes: ["Student at Indian Institute of Technology Bombay"]
tags: ["osre23"]
categories: ["SummerofReproducibility23"]
date: 2023-07-12
lastmod: 2023-07-12
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

As part of the [Reproducible Analysis & Models for Predicting Genomics Workflow Execution Time](https://ospo.ucsc.edu/project/osre23/uga/GenomicsWFModels) my [proposal](https://drive.google.com/file/d/1N81dqvdTDcKjz5WDAUCdf5yi1BNR9Au6/view?usp=sharing) under the mentorship of [In Kee Kim](https://ospo.ucsc.edu/author/in-kee-kim/), Martin Putra and collaborator [Charis Hulu](https://ospo.ucsc.edu/author/charis-christopher-hulu/) (another OSRE fellow) aims to analyze large-scale sequencing datasets in order to gain insights on how ‘input quality’ affects genomic workflows’ execution times.  
Recent advancements in Next-Generation Sequencing (NGS) technologies have resulted in massive amounts of nucleotide sequence data and automated genomic workflows to streamline analysis and data interpretation. The success of NGS-driven research has also led to a sudden increase in data of varying size and complexity, making it more time-consuming for researchers to test hypotheses. Analyzing
high-throughput genomic data requires a step-by-step execution of dedicated tools - also known as workflows. The first step toward the execution of a typical genomic analysis workflow is quality control
of the raw data - a crucial step in removing low-quality data instances that may significantly impact the downstream analysis. Prior work in this area has suggested that the runtimes of genomic workflows get affected due to qualitative differences in the data. Additionally, there is very little consensus on what constitutes “input quality” regarding data from large genomic experiments. In this proposal, we hypothesize that genomic data quality significantly impacts the genomic workflows’ execution time. We aim to leverage machine learning techniques to extract predictive features from quality control tools that robustly predict workflow execution time.
