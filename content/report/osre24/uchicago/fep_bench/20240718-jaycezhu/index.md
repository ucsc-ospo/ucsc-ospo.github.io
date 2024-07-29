---
title: "Mid Term Blog: FEP-Bench: Benchmarking for Enhanced Feature Engineering and Preprocessing in Machine Learning"
subtitle: ""
summary: ""
authors:
 - jaycezhu
tags: ["osre24", reproducibility, "machine learning"]
categories: []
date: 2024-07-18
lastmod: 2024-07-18
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

Hello, I’m {{%mention jaycezhu%}}, a 2024 SoR contributor for the FEP-bench project, under the mentorship of {{% mention yuyangh%}}. The FEP-Bench project proposes to address the significant bottlenecks encountered during this phase, particularly focusing on the challenges posed by data retrieval from data lakes and computational inefficiencies in data operations. By exploring innovative caching, prefetching, and heuristic strategies, this proposal aims to optimize the preprocessing workflow, thereby enhancing efficiency and reducing the required resources of ML projects.

## Motivation
Our research project is based on the context of Deep Neural Networks. To train a DNN, we first need a large amount of data. All raw data must be preprocessed by a data preprocessing pipeline, which is specific to different ML tasks. As usual, in a preprocessing pipeline, the data must be loaded from the disk and converted to the correct format, transformed and augmented. And then, it can be fed into the training stage. In common ML training tasks and datasets, the data preprocessing stage can consume almost 65% of the total training time. However, compared with the fast development of computing hardware including GPUs and TPUs, the speed of data preprocessing pipelines has not been improved by a lot and cannot keep up with these hardware innovations, which leads to a bottleneck in the efficiency of Deep Neural Network training. 

The bottlenecks can be divided into 2 categories: the data side and the computation side. The data side bottleneck is mainly caused by the data transfer in the system, including data fetching, I/O bound, huge size of data, and complex data format. However, the computation side bottleneck can always happen during data preprocessing operations and data shuffling. For distributed Machine Learning training systems, gathering the distributed data can also lead to the computation side bottleneck.

## Current Progress
In order to improve the efficiency of the machine learning preprocessing pipeline, we first need to understand and document the preprocessing workflows commonly used in machine learning, including pipelines of Natural Language Processing, Computer Vision, and Audio datasets. As a result, for the past month, we have built up a collection of common datasets for different machine learning tasks. The dataset types include NLP, CV, Audio, Linear Regression, Video and LiDAR. The machine learning job types are collected based on the dataset types, such as sentiment analysis for NLP, and image classification for CV. The data has either a structured or unstructured format. In addition, our collection contains the following attributes:

- Data/Sample size
- Typical preprocessing operations
- Preprocessing difficulty: hard/easy
- Input splittable
- Output reusable
- CPU/GPU/IO Bound
- Dataset and preprocessing links.

By collecting all this data, we can gain an overview of all common preprocessing pipelines in the current machine learning research field, and build up a solid basis for the next phase of our project, which requires hard work on benchmark profiling. For example, for the Audio datasets, we focus on the LibriSpeech dataset. It contains 1000 hours of speech sampled at 16kHz, making it one of the largest publicly available datasets for speech recognition tasks. The typical preprocessing steps of the LibriSpeech dataset include feature extraction, label to integer conversion, and padding.


## Challenges
During the first phase of the project, I met a lot of challenges as I had not been exposed to topics similar to this project. The first big problem was that I needed to learn the concepts of some machine learning tasks from scratch, such as NLP, so that I could have a better understanding of the common datasets and pipelines. Also, I needed to deeply review a lot of different preprocessing pipelines for each machine learning task, to make the table more comprehensive.
