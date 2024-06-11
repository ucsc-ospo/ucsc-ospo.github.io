---
title: "ML-Powered Problem Detection in Chameleon"
subtitle: ""
summary: ""
authors: [syed]
author_notes: ["PhD Candidate at Boston University"]
tags: ["osre24", reproducibility, "machine learning", "cloud computing"]
categories: [SoR]
date: 2024-06-12
lastmod: 2024-06-12
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

Hello, I am {{%mention syed%}}, a PhD candidate in Electrical and Computer Engineering at Boston University. I will be spending my
summer working on the project [ML-Powered Problem Detection in Chameleon](https://ucsc-ospo.github.io/project/osre24/uchicago/ml_detect_chameleon/) under the mentorship of {{% mention acoskun %}}
and {{% mention msherman %}}.

Currently, Chameleon Cloud monitors sites at the Texas Advanced Computing Center (TACC), University of Chicago,
Northwestern University, and Argonne National Lab. They collect metrics using Prometheus at each site and feed them
all to a central Mimir cluster. All the logs go to a central Loki, and Grafana is used to visualize and set alerts.
Chameleon currently collects around 3000 metrics. Manually reviewing and setting alerts on them is time-consuming
and labor-intensive. This project aims to help Chameleon operators monitor their systems better and improve overall
reliability by creating an anomaly detection service that can augment the existing alerting framework.






