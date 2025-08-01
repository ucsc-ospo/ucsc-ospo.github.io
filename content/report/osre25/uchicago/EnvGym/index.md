---
title: "EnvGym – An AI System for Reproducible Custom Computing Environments"
subtitle: ""
summary:
authors:
  - YimingCheng
tags: ["osre25", "reproducibility", "machine learning", "OS"]
categories: ["osre25", "reproducibility", "EnvGym"]
date: 2025-06-16
lastmod: 2025-06-16
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "EnvGym Project"
  focal_point: Top
  preview_only: false
---

Hello, My name is Yiming Cheng. I am a Pre-doc researcher in Computer Science at University of Chicago. I'm excited to be working with the Summer of Reproducibility and the Chameleon Cloud community as a project leader. My project is [EnvGym](https://github.com/eaminc/envgym) that focuses on developing an AI-driven system to automatically generate and configure reproducible computing environments based on natural language descriptions from artifact descriptions, Trovi artifacts, and research papers.

The complexity of environment setup often hinders reproducibility in scientific computing. My project aims to bridge the knowledge gap between experiment authors and reviewers by translating natural language requirements into actionable, reproducible configurations using AI and NLP techniques.

### Project Overview

EnvGym addresses fundamental reproducibility barriers by:

- Using AI to translate natural language environment requirements into actionable configurations
- Automatically generating machine images deployable on bare metal and VM instances
- Bridging the knowledge gap between experiment authors and reviewers
- Standardizing environment creation across different hardware platforms

### June 10 – June 16, 2025

Getting started with the project setup and initial development:

- I began designing the NLP pipeline architecture to parse plain-English descriptions (e.g., "I need Python 3.9, CUDA 11, and scikit-learn") into structured environment "recipes"
- I set up the initial project repository and development environment
- I met with my mentor Prof. Kexin Pei to discuss the project roadmap and technical approach
- I started researching existing artifact descriptions from conferences and Trovi to understand common patterns in environment requirements
- I began prototyping the backend environment builder logic that will convert parsed requirements into machine-image definitions
- I explored Chameleon's APIs for provisioning servers and automated configuration

### Next Steps

- Continue developing the NLP component for requirement parsing
- Implement the core backend logic for environment generation
- Begin integration with Chameleon Cloud APIs
- Start building the user interface for environment specification

This is an exciting and challenging project that combines my interests in AI systems and reproducible research. I'm looking forward to building a system that will help researchers focus on their science rather than struggling with environment setup issues.

Thanks for reading, I will keep you updated as I make progress on EnvGym!
