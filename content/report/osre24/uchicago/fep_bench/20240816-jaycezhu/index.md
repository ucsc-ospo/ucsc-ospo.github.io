---
title: "Final Blog: FEP-Bench: Benchmarking for Enhanced Feature Engineering and Preprocessing in Machine Learning"
subtitle: ""
summary: ""
authors:
 - jaycezhu
tags: ["osre24", reproducibility, "machine learning"]
categories: []
date: 2024-08-16
lastmod: 2024-08-16
featured: false
draft: false

image:
caption: ""
focal_point: ""
preview_only: false
---

## Background
Hello, I’m {{%mention jaycezhu%}}, a 2024 SoR contributor for the FEP-bench project, under the mentorship of {{% mention yuyangh%}}. Before we started, let's recap the goal of our project and our progress until mid term. The FEP-Bench project proposes to address the significant bottlenecks encountered during this phase, particularly focusing on the challenges posed by data retrieval from data lakes and computational inefficiencies in data operations. In order to solve these challenges, we have collected the basic information of various common datasets for different machine learning tasks, and corresponding preprocessing pipelines.

## Methodology
Since our goal is to improve the efficiency of the machine learning preprocessing pipeline and keep the training process of the Deep Learning model busy, it means that we need to enhance the preprocessing throughput which is the feed rate from the preprocessing stage to the training stage. According to some previous works, we have a new way to look at the Deep Learning Preprocessing Pipelines. The preprocessing pipeline can be split into 2 parts. The first part contains steps that are run once (S1-Sm). We can call it the “offline” part. The second part includes all the rest steps, which are run at every iteration of training. We call it the ”online” part. After the offline preprocessing steps, the output data is written back to disk. Then the online preprocessing steps need to load that data from storage first and do the following operations. We can split the pipeline at any step, and each split is a preprocessing strategy. By using this method, some specific strategies can achieve a much higher final preprocessing throughput. Our project adopts this method to profile the performance of different strategies. And our goal is to maximize the final preprocessing throughput into training, for a specific pipeline. We want to make this an automatic process, rather than ask for extra user instructions or parameters.

## Experiment
Next, we did the data preprocessing strategy experiment on the LibriSpeech dataset, which is an audio dataset for ML tasks like Auto Speech Recognition. The dataset size is 6.3 GB with almost 30000 samples. Each audio file is in a binary format FLAC. As a result, the first step of the preprocessing pipeline we use is decoding, which converts the binary data into arrays of floats. Then we applied some typical audio preprocessing steps of transformation (normalization, padding, extract loudest section) and augmentation (random cut, random shift audio, random mask, random add noise) to audio data. Finally, the audio data is converted to Log-Mel Spectrogram signal, which is commonly used in audio tasks like Speech Recognition and Speaker identification. 

We have benchmarked the throughput performance and storage overhead of all possible strategy split points, and have seen some trade-offs between them. Both storage overhead and throughput speed-up use the fully online method as the baseline. What we've observed from our results is that the speed-up keeps increasing when we put operations into the offline part, and the storage consumption is very low for the strategies after audio decoding. Also, we analysed the performance of individual methods of transformation and augmentation steps. We find that the speed-up performance is quite stable between 1.0 and 1.2 across these methods, but some methods can have a high storage overhead, like normalization and random noise.

Another thing we observed during our experiments is that different dataset sizes can influence the preprocessing pipeline throughput. We found that the throughput speed-up of 10000 samples is almost double the speed-up of 5000 samples. It seems like a larger dataset size may lead to a higher speed-up. So, we were thinking that does every operation follows this pattern or only certain operations can have increasing throughput with increasing dataset size, and then did experiments about the throughput speed-ups on different dataset sizes of all operations in the audio preprocessing pipeline. The results showed that only the audio decoding step can have a great increase in speed-up for larger dataset sizes. But for transformation, augmentation and LMS, the throughputs always stay at a steady level. This indicates that the only audio decoding step can become faster and faster when the dataset size grows.

## Conclusion
In our work, we have built up a collection of common datasets and their preprocessing pipelines for different machine-learning tasks. For the audio dataset LibriSpeech, we have done experiments about the trade-offs between throughput speed-ups and storage overhead, and dataset sizes. We have found that speed-ups keep increasing when more and more operations are divided into the offline part. Only the audio decoding step can become faster and faster when the dataset size grows.

## Future works
In the near future, we still want to find the optimal preprocessing strategy by profiling only a small part of the original enormous dataset. The second thing is that besides the audio dataset, we must expand the range of our experiments on other datasets and ML tasks. Finally, we need to implement our goal of building an automatic system that decides the optimal strategy of a preprocessing pipeline.
