---
title: "Final Blogpost: Drift Management Strategies Benchmark"
subtitle: "Evaluating approaches in tackling drifts"
summary: ""
authors: 
  - williamn
tags: ["osre24", reproducibility]
categories: []
date: 2024-08-24
lastmod: 2024-08-24
featured: true
draft: false

# Featured image

# To use, add an image named `featured.jpg/png` to your page's folder.

# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.

image:
caption: ""
focal_point: ""
preview_only: false
---

# Background
Hello there! I'm William and this is my final blog for my proposal "Developing A Comprehensive Pipeline to Benchmark Drift Management Approaches" under the mentorship of [Ray Andrew](https://ucsc-ospo.github.io/author/ray-andrew-sinurat/) and [Sandeep Madireddy](https://ucsc-ospo.github.io/author/sandeep-madireddy/) under the [LAST](/project/osre24/anl/last) project.

If you're not familiar with it, this project aims to address the issue of model aging, where machine learning (ML) models experience a decline in effectiveness over time due to environmental changes, known as drift. My goal is to design an extensible pipeline that evaluates and benchmarks the robustness of state-of-the-art algorithms in addressing these drifts. 

# Deliverables
You can find my list of deliverables here:
- [Final report](https://docs.google.com/document/d/14tSmBndX1RBv_d3luRcqFDmbuMk6XsGOB8G7tzTcHnE/edit), this blog is a summarized version of my final report, so do take a look if you'd like to know more!
- [Github repository](https://github.com/williamnixon20/osre-drift), contains code as well as the raw experiment results.
- [Trovi artifact](https://www.chameleoncloud.org/experiment/share/e3ae5f07-4340-48c0-94e8-ba99ee2bf691)

# Evaluation
Here are some of the graphs that show the performance of every algorithm on the created datasets. For more graphs and figures, you can check out my final report:
- CIRCLE: AUE demonstrates stability, maintaining a high accuracy even as the data drifts, which may be due to its ensemble nature. It is even more stable than baseline retraining algorithms. Matchmaker is also able to recover quickly upon experiencing drift, which maybe again due to its ranking the most high performing models to do inference, recovering faster than RetrainWin. On the other hand, DriftSurf experiences several random drops in accuracy, indicating that it can be somewhat unstable. 
![Circle](circle.jpg)
- SINE: Similar to CIRCLE, AUE demonstrates stability throughout the dataset, maintaining a high accuracy even as the data drifts. Matchmaker however was struggling to adapt as fast when encountering such a sudden drift, as it needed some time/windows to recover from the drop. Driftsurf's performance was notably better than baseline, as unlike them, it was able to recover successfully fairly quickly upon experiencing drift.
![Sine](sine.jpg)
- CovCon: In CovCon, Matchmaker was able to achieve the best accuracy, as it is able to select the models most relevant to each incoming batch (model trained on the most similar features), performing comparably to retrain window. Most of the other algorithms suffered in this dataset, particularly AUE whose performance is now becoming comparable to the rest of the algorithms and baseline.
![CovCon](covcon.jpg)
- IOAdmission: Performance on this dataset was led by AUE, which was able to maintain impressive stability amongst all of the algorithms used. This is followed closely by Matchmaker. The other algorithms used undergo a lot of fluctuations in accuracy.
![IOAdmission](ioadm.jpg)


# Findings / Discussion
From the experiments conducted, the findings are as follows:
- Matchmaker was able to perform particularly well in CovCon, SINE and IO Admission dataset. This maybe due to its ability to choose the most relevant trained model from its ensemble during inference time. Its training time is also the best compared to other algorithms, especially considering that it keeps data for training an additional random forest model for ranking the models. However, its inference time was the longest amongst all other algorithms. This may be due to the fact that on inference time, one needs to traverse all of the leaf nodes of the random forest used to rank it (computing covariate shift). 

- AUE was able to perform particularly well in the CIRCLE dataset. However, it is quite competitive on other datasets too. It's weighting function which incentives highly relevant models and eviction of less relevant ones may be key. Its inference time is decent compared to other algorithms, slower than most baselines and Driftsurf, but faster than Matchmaker. However, it's training time took the longest amongst other competitors, as it has an expensive weighting function to weight, evict, or retrain models on every retraining.

- DriftSurf was performing very similarly to baseline, particularly the RetrainWindow, in almost all datasets. However unlike the retrain window which achieved such performance with remembering 7 windows prior, Driftsurf was able to achieve comparable performance with only 2 windows. However, it needs to train 2 models at every iteration. On the plus side, its inference time is comparable to the baseline single model, having almost no inference overhead compared to most of the competitors out there. Another plausible explanation for the lack of performance is the lack of tuning, such as the number of windows retained, the length of its reactive period, and its reactivity sensitivity threshold. A better performance could be achieved if these parameters were tuned further.


# Next Steps
These are some of the potential extensions for this project:
1. Optimize Matchmaker's inference time improving Matchmaker's efficiency, especially in covariate shift ranking, can reduce inference time. Simplifying the random forest traversal could make Matchmaker faster without impacting performance.
2. Extending the work to include other frameworks like TensorFlow or PyTorch, as it can now only support a scikit-learn base model.


Thank you for reading!