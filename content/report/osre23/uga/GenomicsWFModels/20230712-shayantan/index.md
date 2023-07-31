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


We are currently midway into the OSRE 2023 program and the following post lists the progress that I have made on the project so far.
As part of the [Reproducible Analysis & Models for Predicting Genomics Workflow Execution Time](/project/osre23/uga/GenomicsWFModels) our overall goal was to enumerate the effect of sequence data quality on execution times. Towards that end, we decided to first identify suitable datasets from the two commmonly available -omics data modalities - transcriptomics and genomics. Albrecht et al. [1] developed ***seqQscorer*** to automate the quality control step of NGS data analysis through predictive modeling. They have also published the list of ENCODE datasets used for training the models. Quality label has been assigned as 0 for released files or 1 for revoked files. Based on the guidelines set forth by ENCODE's Data Coordination Centre (DCC) a comprehensive manual annotation of the data was done by scientists and the resulting quality variable "status" was published to serve as an indication of the quality of the data. The following steps outline the process of generating the data table for building the machine learning models. 
* Step 1: Programmatically accessed 86 (34 released ; 34 revoked) RNA-seq files from ENCODE database. All the fastq files were single ended.
* Step 2: Programmatically accessed 288 (144 released ; 144 revoked) DNA-seq files from ENCODE database. All the fastq files were paired ended.
* Step 3: Implemeted the STAR aligner for RNA-seq and the BWA aligner for DNA seq. The resulting outputs contained the alignment times for both the "revoked" and "released". 
* Step 4: Ran statistical tests to determine whether there is any significant differences in the runtimes of both types of files.

Currently I am running the FASTQC tool to extract data quality metrics for the same set of files as discsussed above. Once I have collected those metrics, I can start building regression models to determine whether there is any significant impact of data quality on execution time. The first step toward the execution of a typical genomic analysis workflow is quality control of the raw data - a crucial step in removing low-quality data instances that may significantly impact the downstream analysis. Through our analysis we aim to develop a reproducible ML model that will give the user an estimate of the runtime based on the raw FATSQ file as input.  

References
[1] Albrecht, S., Sprang, M., Andrade-Navarro, M.A. _et al._ seqQscorer: automated quality control of next-generation sequencing data using machine learning. _Genome Biol_  **22**, 75 (2021). https://doi.org/10.1186/s13059-021-02294-2

