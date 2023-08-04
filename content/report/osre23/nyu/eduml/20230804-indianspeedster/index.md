---
title: "Using Reproducibility in Machine Learning Education: Reproducibility with Incomplete Methodology Descriptions"
subtitle: ""
summary: ""
authors: [indianspeedster]
author_notes: ["Student at New York University "]
tags: ["osre23"]
categories: ["SummerofReproducibility23"]
date: 2023-08-04
lastmod: 2023-05-21
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

Hey,

I am Shekhar and I am one of several students who are working on developing materials for reproducibility in machine learning education, under the mentorship of  {{%mention ffund %}}. My [Proposal](https://drive.google.com/file/d/1rCzLGIJ8HYCVjY_MfndgrQjAQa2SQbqZ/view?usp=sharing) aims to develop interactive educational materials about reproducibility in machine learning, for use in graduate and undergraduate classes. Our goal is to help students and researchers (1) understand some of the challenges they may face when trying to reproduce someone else's published result, and (2) in their own publications, to specify the methodology so that the result will be more easily reproduced by others. 

## Motivation

My work is inspired by my participation in the [2022 Machine Learning Reproducibility Challenge](https://paperswithcode.com/rc2022), where I was reproducing a result related to bias in hate speech classifiers. The paper seemed at first to have complete methodology details. However, when I tried to implement their approach based on the description of the paper, I realized some important details were missing - for example, in the part where they replaced swear words in the text with other words having similar meaning. I wasn't able to identify the exact list of swear words they used, or what approach they followed if the selected replacement was also a swear word. The choices I made when the authors' approach was left ambiguous had a significant impact on the magnitude of the final result.


## Milestones and Accomplishments

To inform researchers and students about this problem, I created a fictitious machine learning research paper, and a sequence of accompanying Python notebooks to highlight various choices that can be made to fill in the gaps, and explore how these choices can impact the overall results of the research. Our "research paper" is about the impact of data augmentation on few-shot learning for intent classification.  We implemented a basic data augmentation strategy with synonym replacement using the HWU64 dataset and a BERT classifier, and the results suggest that synonym replacement as a data augmentation technique leads to only minor improvement in accuracy.
In the fictitious paper, we left some of the methodology details ambiguous. When reproducing the results using the accompanying notebooks, the reader follows a "Choose Your Own Adventure" format, selecting a path through a tree, where each node represents ambiguous methodology details and branches out to different choices that are made at that instance. The leaf nodes will represent the final results, providing insights into the magnitude of the differences resulting from each node selection. Some of the choices that the reader makes are - 

- what subset of the source dataset to use.
- some of the details of data pre-processing.
- some of the details of the synonym replacement data augmentation strategy.
- some training hyperparameters and the details of the hyperparameter search.


During the first phase of our project, we have implemented an initial draft of these notebooks, to explore various scenarios and see their impact on results. Next, we will further develop the interactive educational material around them.


## Challenges

During the first half of the project, I faced two main challenges. First, I had to come up with a hypothetical research scenario that was realistic, yet easy for students without much expertise to understand. Attaining the right balance was essential to make it engaging and educational. The second challenge was to deliberately leave some details unclear in a realistic way while ensuring that the choices based on that ambiguity had a significant impact on the results. Fortunately, I had the guidance and support of my mentor, which allowed me to successfully tackle these challenges.

Throughout this project, I faced various challenges and obstacles, but it turned out to be an incredible learning experience. I had the opportunity to dive deep into the domains of few-shot learning and meta-learning, which were entirely new to me. Moreover, I was able to find ambiguous methodologies present in academic papers and explore diverse scenarios related to them. Looking ahead, I am eager to continue working on this project throughout the summer, as it promises further learning and personal growth.


