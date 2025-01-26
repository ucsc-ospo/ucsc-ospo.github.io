---
title: "Halfway Through GSOC: My Experience and Learnings"
subtitle: "BenchmarkST: Cross-Platform, Multi-Species Spatial Transcriptomics Gene Imputation Benchmarking"
summary: ""
authors: [qianru]
tags: ["osre24", reproducibility, machine learning, bioinformatics, spatial transcriptomics]
categories: []
date: 2024-07-18
lastmod: 2023-07-18
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

Hello there! I'm Qianru, and this is my mid-term blog post for the 2024 Google Summer of Code. I am working on the BenchmarkST project, focusing on benchmarking gene imputation methods in spatial transcriptomics. My goal is to create a comprehensive, reproducible platform for evaluating these methods across various datasets and conditions.

In this post, I will share some of the progress I have made so far, the challenges I have faced, and how I overcame them. I will also highlight some specific accomplishments and what I plan to do next.

---



### Achievements:
1. **Developed the Python Package:** I created the "Impeller" Python package, which includes tools for downloading example data, processing it, and training models. This package aims to standardize gene imputation tasks in spatial transcriptomics.
2. **Example Data Integration:** Successfully integrated various spatial transcriptomics datasets into the package for benchmarking purposes.
3. **Benchmarking Framework:** Established a framework for objective comparison of different gene imputation methodologies.

**Python Package: Installation and Usage**

You can install the package using pip:

```bash
pip install Impeller
```

Download Example Data
```bash
from Impeller import download_example_data
download_example_data()
```

Load and Process Data
```bash
from Impeller import load_and_process_example_data, val_mask, test_mask, x, original_x = load_and_process_example_data()
```

Train Model
```bash
from Impeller import create_args, train args = create_args(),test_l1_distance, test_cosine_sim, test_rmse = train(args, data, val_mask, test_mask, x, original_x)
```

---



### Challenges:
Reproducing the results of various gene imputation methods was not an easy task. I faced several challenges along the way:
1. **Lack of Standardized Data:** Some methods had incomplete or missing code, making it difficult to reproduce their results accurately.
2. **Reproducibility Issues:** Successfully integrated various spatial transcriptomics datasets into the package for benchmarking purposes.
3. **Resource Limitations:** Running large-scale experiments required significant computational resources, which posed constraints on the project timeline.


---



### Future Work:
Moving forward, I plan to:
1. Extend the package's functionalities to include more datasets and imputation methods.
2. Enhance the benchmarking framework for more comprehensive evaluations.
3. Collaborate with other researchers to validate and improve the package's utility in the bioinformatics community.

---


I hope you found this update informative and interesting. If you have any questions or feedback, please feel free to contact me. Thank you for your attention and support!
