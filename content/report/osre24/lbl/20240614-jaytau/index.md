---
title: Drishti
subtitle: Visualization and Analysis of AI-based Applications
summary:
authors: 
  - jaytau
tags: ["osre24", "uc", "LBNL", "data science", "visualization", "performance analysis", "I/O", "HPC", "AI"]
categories: ["GSoC'24"]
date: 2024-06-06
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

Namaste everyone! 🙏🏻

I'm [Joel Tony](https://www.jaytau.com?ref=uc-ospo), a third-year Computer Science student at BITS Pilani, Goa, India. I'm truly honoured to be part of this year's Google Summer of Code program, working with the UC OSPO organisation on a project that genuinely excites me. I'm particularly grateful to be working under the mentorship of Dr. {{% mention jeanlucabez %}}, a Research Scientist at Lawrence Berkeley National Laboratory, and Dr. [Suren Byna](https://sbyna.github.io), a Full Professor at the Ohio State University. Their expertise in high-performance computing and data systems is invaluable as I tackle this project.

My project, "[Drishti: Visualization and Analysis of AI-based Applications](/project/osre24/lbl/drishti)", aims to extend the [Drishti](https://github.com/hpc-io/drishti) framework to better support AI/ML workloads, focusing specifically on optimizing their Input/Output (I/O) performance. I/O refers to the data transfer between a computer's memory and external storage devices like hard drives (HDDs) or solid-state drives (SSDs). As AI models and datasets continue to grow exponentially in size, efficient I/O management has become a critical bottleneck that can significantly impact the overall performance of these data-intensive workloads.

Drishti is an innovative, interactive web-based framework that helps users understand the I/O behaviour of scientific applications by visualising I/O traces and highlighting bottlenecks. It transforms raw I/O data into interpretable visualisations, making performance issues more apparent. Now, I'm working to adapt these capabilities for the unique I/O patterns of AI/ML workloads.

Through my studies in high-performance computing and working with tools like BeeGFS and Darshan, I've gained insights into the intricacies of I/O performance. However, adapting Drishti for AI/ML workloads presents new challenges. In traditional HPC, computing often dominates, but in the realm of AI, the tables have turned. As models grow by billions of parameters and datasets expand to petabytes, I/O has become the critical path. Training larger models or using richer datasets doesn't just mean more computation; it means handling vastly more data. This shift makes I/O optimisation not just a performance tweak but a fundamental enabler of AI progress. By fine-tuning Drishti for AI/ML workloads, we aim to pinpoint I/O bottlenecks precisely, helping researchers streamline their data pipelines and unlock the full potential of their hardware.

As outlined in my [proposal](https://docs.google.com/document/d/1zfQclXYWFswUbHuuwEU7bjjTvzS3gRCyNci08lTR3Rg/edit?usp=sharing), my tasks are threefold:

1. **Modularize Drishti's codebase**: Currently, it's a single 1700-line file that handles multiple functionalities. I'll be refactoring it into focused, maintainable modules, improving readability and facilitating future enhancements.
2. **Enable multi-trace handling**: Unlike traditional HPC apps that typically generate one trace file, most AI jobs produce multiple. I'll build a layer to aggregate these, providing a comprehensive view of the application's I/O behaviour.
3. **Craft AI/ML-specific recommendations**: Current suggestions often involve MPI-IO or HDF5, which aren't typical in ML frameworks like PyTorch or TensorFlow. I'll create targeted recommendations that align with these frameworks' data pipelines.

This summer, my mission is to make Drishti as fluent in AI/ML I/O patterns as it is in traditional HPC workloads. My goal is not just to adapt Drishti but to optimise it for the unique I/O challenges that AI/ML applications face. Whether it's dealing with massive datasets, handling numerous small files, or navigating framework-specific data formats, we want Drishti to provide clear, actionable insights.

From classroom theories to hands-on projects, from understanding file systems to optimising AI workflows, each step has deepened my appreciation for the complexities and potential of high-performance computing. This GSoC project is an opportunity to apply this knowledge in a meaningful way, contributing to a tool that can significantly impact the open-source community.

In today's AI-driven world, the pace of innovation is often gated by I/O performance. A model that takes weeks to train due to I/O bottlenecks might, with optimised I/O, train in days—translating directly into faster iterations, more experiments, and ultimately, breakthroughs. By making I/O behaviour in AI/ML applications more interpretable through Drishti, we're not just tweaking code. We're providing developers with the insights they need to optimise their data pipelines, turning I/O from a bottleneck into a catalyst for AI advancement.

I look forward to sharing updates as we adapt Drishti for the AI era, focusing squarely on optimising I/O for AI/ML workloads. In doing so, we aim to accelerate not just data transfer but the very progress of AI itself. I'm deeply thankful to Dr. Jean Luca Bez and Prof. Suren Byna for their guidance in this endeavour and to the UC OSPO and GSoC communities for this incredible opportunity.
