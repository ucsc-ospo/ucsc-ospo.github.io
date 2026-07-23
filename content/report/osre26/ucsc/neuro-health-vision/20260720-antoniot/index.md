---
title: "Midterm Blog of NeuroHealth-Vision: Leveraging Clinical Insights as Priors for Medical Foundation Models"
subtitle: "Learning from clinical guidance and preparing the foundations for volumetric pretraining"
summary: "Building a clinically grounded pretraining pipeline for volumetric medical data, with several learning objectives and a path toward systematic architecture benchmarking."
authors:
  - antoniot
tags: ["osre26", "NeuroHealth-Vision"]
categories: ["osre26", "NeuroHealth-Vision"]
date: 2026-07-20
lastmod: 2026-07-20
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Connecting clinical CT workflows with volumetric pretraining"
  focal_point: "Center"
  preview_only: false
---

## Refresher About the Project

**NeuroHealth-Vision** is my Google Summer of Code 2026 project through UCSC OSPO, under the mentorship of **Dr. Linsey Pang** and **Dr. Bin Dong**. The project explores how foundation models can learn useful representations from volumetric medical imaging.

Unlike an ordinary two-dimensional image, a CT study is a three-dimensional volume whose interpretation depends on spatial relationships, anatomy, acquisition protocols, and intensity information across many slices. NeuroHealth-Vision investigates training objectives and model designs that can better account for these properties.

The broader goal is to establish reproducible methods for learning and evaluating volumetric representations while keeping conclusions tied to the clinical settings and downstream tasks that are actually tested.

## Key Milestones So Far

### Developing Clinical Grounding

A major focus of the first half of the project has been connecting model development with the clinical realities of volumetric CT imaging. I conducted an extensive review of clinical guidelines and imaging workflows through literature study, technical investigation, and interviews with radiologists affiliated with major healthcare institutions across two countries.

This work examined how CT studies progress from scan preparation and protocol setup through image acquisition, reconstruction and phase selection, workstation reformats, anatomical interpretation, image-quality assessment, and structured clinical reporting. Studying the full workflow has helped clarify how decisions made at each stage affect the volumes presented to a model—and what questions a clinically meaningful evaluation should ask.

### Establishing Objective Benchmarks

On the modeling side, I implemented several pretraining objectives beyond a standard cross-entropy loss baseline. These objectives provide reference points for studying how different learning signals shape representations of three-dimensional clinical data.

At this stage, they serve as experimental benchmarks rather than final conclusions about which objective is most effective.

### Building the Pretraining Pipeline

I also designed and implemented a pretraining pipeline for volumetric foundation-model training. The pipeline provides a shared foundation for running controlled experiments across different objectives and, as development continues, different model architectures.

Having this common infrastructure in place should make subsequent comparisons more consistent and reproducible.

## Next Steps

The immediate next step is to implement, test, and benchmark a selection of model architectures for volumetric pretraining. Once the architecture baselines are established, I plan to evaluate selected combinations of model architecture and pretraining objective under a consistent experimental setup.

These comparisons will help identify which directions are most promising for deeper evaluation during the remainder of the project.
