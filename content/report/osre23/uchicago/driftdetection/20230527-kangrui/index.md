---
title: "Automatic Cluster Performance Shifts Detection Toolkit"
subtitle: ""
summary: "This project aims to design a real-time performance shift detection algorithm for high-performance computing clusters, ensuring minimal overheads."
authors: [Kangrui Wang]
author_notes: ["Master Student at The University of Chicago"]
tags: ["osre23"]
categories: [SoR'23]
date: 2023-05-27
lastmod: 2023-05-27
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
Hi! I am Kangrui, a Pre-doc student at the University of Chicago. As part of the [Automatic Cluster Performance Shifts Detection Toolkit](/project/osre23/uchicago/driftdetection) my [proposal](https://drive.google.com/file/d/1AxpgWLzF3oKTFlD8q6JYS35CxxJ6c76X/view?usp=share_link)under the mentorship of {{% mention sandeep %}} aims to design a real-time performance shift detection algorithm for high-performance computing clusters, ensuring minimal overheads.

This project focuses on developing a real-time performance shift detection algorithm tailored to heterogeneous workloads, aiming to promptly inform administrators about performance changes. The primary goal is to design an algorithm that efficiently detects shifts in real-time, with minimal system overheads.

In addition to algorithm development, we plan to enhance the Darshan toolkit's functionality by integrating our algorithm, offering users early performance shift detection. This integration will aid administrators in making informed system utilization and scheduling decisions.

To promote transparency and reproducibility, we'll encapsulate our findings, scripts, and profiling data within a Jupyter notebook, especially Chameleon Trovi, enabling other researchers to reproduce our experiments easily.

Looking ahead, we plan to expand the algorithm's applicability to cater to diverse HPC workloads and infrastructures. Other areas of interest include its use in detecting shifts in financial markets or monitoring IoT data streams. Further refinement of our algorithm, to reduce overheads and improve real-time detection capabilities, is also a part of our future endeavours. This task may involve evaluating various shift detection methods and noise filtering techniques.
