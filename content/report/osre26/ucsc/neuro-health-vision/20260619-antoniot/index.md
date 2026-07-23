---
title: "Introducing NeuroHealth-Vision: A Volumetric Perception Module for Multimodal Clinical Reasoning"
subtitle: "How can foundation models understand volumetric medical imaging?"
summary: "Exploring novel, domain-adapted and medically informed pretraining objectives for volumetric medical data, alongside improved methods for evaluating volumetric foundation models."
authors:
  - antoniot
tags: ["osre26", "NeuroHealth-Vision"]
categories: ["osre26", "NeuroHealth-Vision"]
date: 2026-06-19
lastmod: 2026-06-19
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "From volumetric CT imaging to foundation-model reasoning"
  focal_point: "Center"
  preview_only: false
---

Hi! I’m **Antonio Tan**, and I’m interested in multimodal AI and how machine learning systems can reason across different forms of data. Outside of research, I enjoy soccer and Texas Hold’em.

This summer, I will be working on **NeuroHealth-Vision** through OSRE 2026 under the mentorship of **Dr. Linsey Pang** and **Dr. Bin Dong**. You can read my [original project proposal](proposal.pdf) for more details about the project’s initial direction.

## Beyond text and 2D images

Large language models have become increasingly capable of understanding clinical text, while frontier computer-vision models have made substantial progress on ordinary two-dimensional images. Volumetric medical imaging, however, presents a different and less explored challenge.

A CT study is a three-dimensional volume composed of many spatially related slices. Clinically meaningful information may depend on anatomical structure, intensity values, acquisition protocols, and relationships across the full volume—properties that are difficult to capture by treating each slice as an independent image. Models trained on one type of CT data may also struggle when transferred to another anatomical region, imaging protocol, or clinical task.

This leads to the central question behind my project: **How can foundation models better understand volumetric medical imaging?**

## The project

NeuroHealth-Vision will explore how foundation models can learn useful representations from volumetric CT data. In particular, the project will investigate domain-adapted and medically informed learning objectives, alongside methods for evaluating whether volumetric foundation models transfer effectively to specialized clinical settings.

Rather than attempting to cover every form of CT imaging, the work will focus on selected imaging types and downstream tasks as preliminary case studies. An important foundation will be developing reproducible pipelines for preparing CT volumes, potentially including voxel resampling, intensity normalization, medical image windowing, and spatial alignment. These pipelines will support experiments comparing representation-learning and model-adaptation strategies.

More broadly, the project aims to identify where existing models succeed, where they struggle, and what kinds of medical or domain-specific knowledge may help close the gap.

## Looking ahead

I look forward to learning more about volumetric medical imaging, contributing reproducible open-source tools, and sharing the project’s technical decisions and results as the summer progresses.
