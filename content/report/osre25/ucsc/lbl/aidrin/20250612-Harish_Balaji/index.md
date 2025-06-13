---
title: "Improving AI Data Pipelines in AIDRIN: A Privacy-Centric and Multimodal Expansion"
summary: Enhancing AIDRIN with privacy metrics and multimodal support under mentorship from LBNL researchers as part of GSoC 2025.
authors: 
- harishbalaji
- jeanlucabez
- surenbyna
tags: [
  "AIDRIN",
  "AI readiness",
  "data quality",
  "dataset privacy",
  "GSoC2025",
  "HPC",
  "LBNL",
  "Lawrence Berkeley Lab",
  "lbl",
  "open source",
  "osre25",
  "UCB",
  "UC",
  "University of California Berkeley"
]

categories: ["Google Summer of Code", "GSoC 2025", "Open Source", "AI Readiness"]

date: 2025-06-12
lastmod: 2025-06-12
featured: true
draft: false
user_groups:
- 2025 Contributors

# Featured image
image:
  caption: "AIDRIN - inspecting dataset readiness for AI pipelines"
  focal_point: Top
  preview_only: false
---

⏱️ Reading time: 4–5 minutes

Hi 👋

I’m Harish Balaji, a Master’s student at NYU with a focus on Artificial Intelligence, Machine Learning, and Cybersecurity. I’m especially interested in building scalable systems that reflect responsible AI principles. For me, data quality isn’t just a technical detail. It’s a foundational aspect of building models that are reliable, fair, and reproducible in the real world.

This summer, I’m contributing to AIDRIN (AI Data Readiness Inspector) as part of Google Summer of Code 2025. I’m grateful to be working under the mentorship of Dr. Jean Luca Bez and Prof. Suren Byna from the [Scientific Data Management Group](https://crd.lbl.gov/divisions/scidata/sdm/) at Lawrence Berkeley National Laboratory (LBNL).

AIDRIN is an open-source framework that helps researchers and practitioners evaluate whether a dataset is truly ready to be used in production-level AI workflows. From fairness to privacy, it provides a structured lens through which we can understand the strengths and gaps in our data.

## Why this work matters

In machine learning, one principle always holds true:  
> "Garbage in, garbage out."

Even the most advanced models can underperform or amplify harmful biases if trained on incomplete, imbalanced, or poorly understood data. This is where AIDRIN steps in. It provides practical tools to assess datasets across key dimensions like privacy, fairness, class balance, interpretability, and support for multiple modalities such as images, text, and audio.

By making these characteristics measurable and transparent, AIDRIN empowers teams to make informed decisions early in the pipeline. It helps ensure that datasets are not only large or complex, but also trustworthy, representative, and purpose-fit.

## My focus this summer

As part of my GSoC 2025 project, I’ll be focusing on extending AIDRIN’s evaluation capabilities. A big part of this involves strengthening its support for privacy metrics and designing tools that can handle non-tabular datasets, such as image-based data.

The goal is to expand AIDRIN’s reach without compromising on interpretability or ease of use. More technical insights and updates will follow in the next posts as the summer progresses.

## What comes next

As the AI community continues to evolve, there’s a growing shift toward data-centric practices. I believe frameworks like AIDRIN are essential for helping us move beyond the question of *"Does the model work?"* toward a deeper and more meaningful one: *"Was the data ready in the first place?"*

Over the next few weeks, I’ll be working on development, testing, and integration. I’m excited to contribute to a tool that emphasizes transparency and reproducibility across the AI lifecycle, and to share lessons and ideas with others who care about responsible AI.

If you’re exploring similar challenges or working in the space of dataset evaluation and readiness, I’d love to connect and exchange thoughts. You can also read my full GSoC 2025 proposal below for more context around the project scope and vision:

👉 [Read my GSoC 2025 proposal here](https://drive.google.com/file/d/1RUyU2fHkc8GZ9vTj5SUr6jj84ZaRUvNt/view)

*This is the first in a 3-part blog series documenting my GSoC journey with AIDRIN. Stay tuned for technical updates and behind-the-scenes insights as the summer unfolds!*
