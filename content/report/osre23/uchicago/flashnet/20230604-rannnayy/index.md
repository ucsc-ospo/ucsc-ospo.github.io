---
title: "FlashNet: Towards Reproducible Continual Learning for Storage System"
subtitle: ""
summary: ""
authors: [rannnayy]
author_notes: ["Student at Institut Teknologi Bandung"]
tags: ["osre23"]
categories: [SoR'23]
date: 2023-06-04
lastmod: 2023-06-04
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

Hello! I'm Rani, a third year undergraduate student at Institut Teknologi Bandung majoring at Informatics. As part of the [FlashNet](/project/osre23/uchicago/flashnet) my [proposal](https://drive.google.com/file/d/1EhJm3kqrpybOkpXiiRMfqVxGeKe9iIsh/view?usp=sharing) under the mentorship of **Haryadi S. Gunawi** and **Daniar Kurniawan** aims to implement and optimize the FlashNet model in real-world storage systems using continual learning techniques.

In real world workloads, it is known that the I/O stream changes and varies. Hence, the performance of I/O read/write could vary and introduce the tail latency. We would like to predict the latency of I/O read to cut the tail and improve the system's performance. This project focuses on improving the FlashNet pipeline and introducing adaptability to the machine learning models built.

During the summer, we planned to implement the continual learning pipeline using machine learning models we have built previously in the project. Of course, continual learning isn't a continual learning without the ability of self-motivated retraining. Thus, we will implement several drift detection algorithms, evaluate, and test them. Besides, we will also build a visualization platform to evaluate and monitor the performance of the models built. Lastly, we planned to create Chameleon Trovi artifacts to demonstrate our experiments and make these implementations available and reproducible to the public.
