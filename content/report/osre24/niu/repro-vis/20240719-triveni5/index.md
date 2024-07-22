---
title: "Reproducibility in Data Visualization"
subtitle: "Categorize Differences in Reproduced Visualizations"
summary: ""
authors: [triveni5]
tags: ["osre24", reproducibility]
categories: [SoR]
date: 2024-07-19
lastmod: 2024-07-19
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
Hello everyone!

I'm Triveni, a Master's student in Computer Science at Northern Illinois University (NIU). I'm excited to share my progress on the OSRE 2024 project [Categorize Differences in Reproduced Visualizations](https://ucsc-ospo.github.io/project/osre24/niu/repro-vis/) focusing on data visualization reproducibility. Working under the mentorship of [David Koop](https://ucsc-ospo.github.io/author/david-koop/), I've made some significant strides and faced some interesting challenges.

## Initial Approach and Challenges
I began my work by comparing original visualizations with reproduced ones using OpenCV for pixel-level comparison. This method helped highlight structural differences but also brought to light some challenges. Different versions of libraries rendered visualizations slightly differently, causing minor positional changes that didn't affect the overall message but were still flagged as discrepancies.

To address this, I experimented with machine learning models like VGG16, ResNet, and Detectron2. These models are excellent for general image recognition but fell short for our specific needs with charts and visualizations. The results were not as accurate as I had hoped, primarily because these models aren't tailored to handle the unique characteristics of data visualizations.

## Shifting Focus to Chart-Specific Models
Recognizing the limitations of general ML models, I shifted my focus to chart-specific models like ChartQA, ChartOCR, and ChartReader. These models are designed to understand and summarize chart data, making them more suitable for our goal of comparing visualizations based on the information they convey.

## Generating Visualization Variations and Understanding Human Perception
Another exciting development in my work has been generating different versions of visualizations. This will allow me to create a survey to collect human categorization of visualizations. By understanding how people perceive differences whether it's outliers, shapes, data points, or colors. We can gain insights into what parameters impact human interpretation of visualizations.

## Next Steps
Moving forward, I'll continue to delve into chart-specific models to refine our comparison techniques. Additionally, the survey will provide valuable data on human perception, which can be used to improve our automated comparison methods. By combining these approaches, I hope to create a robust framework for reliable and reproducible data visualizations.

I'm thrilled about the progress made so far and eager to share more updates with you all. Stay tuned for more insights and developments on this exciting journey!

