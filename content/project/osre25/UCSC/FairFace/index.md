---
title: "Understanding Skin-Tone based Bias in Text-to-Image Models Using Stable Diffusion"
date: 2025-05-27
lastmod: 2025-05-27
authors: ["Marzia Binta Nizam", "James Davis"]
tags: ["osre25", "uc", "bias", "stable-diffusion"]
---

This project investigates **skin tone bias in text-to-image generation** by analyzing the output of **Stable Diffusion** models when prompted with socially and occupationally descriptive text. Despite the growing popularity of generative models like Stable Diffusion, little has been done to evaluate how these models reproduce or amplify visual bias—especially related to **skin tone, perceived race, and social class**—based solely on textual prompts.

This work builds on prior studies of bias in large language models (LLMs) and vision-language models (VLMs), and aims to explore how biases manifest visually, without explicitly specifying race or ethnicity in the input prompt. Our approach combines **systematic prompt generation**, **model-based image creation**, and **skin tone quantification** to assess disparities across generated samples.

The ultimate goal is to develop a **reproducible evaluation pipeline**, visualize disparities across demographic and occupational prompts, and explore strategies to mitigate representational harms in generative models.


Our goal is to create a reproducible pipeline for:
- Generating images from prompts
- Annotating or analyzing them using computer vision tools
- Measuring bias across categories like skin tone, gender presentation, or status markers

Project webpage: [https://github.com/marzianizam/ucsc-ospo.github.io/tree/main/content/project/osre25/UCSC/FairFace](https://github.com/marzianizam/ucsc-ospo.github.io/tree/main/content/project/osre25/UCSC/FairFace)

### Project Idea: Measuring Bias in AI-Generated Portraits

- **Topics**: Responsible AI, Generative Models, Ethics in AI
- **Skills**: Python, PyTorch, Stable Diffusion, Prompt Engineering, Data Analysis
- **Difficulty**: Medium
- **Size**: 350 hours
- **Mentors**: 
  - {{% mention "Marzia Binta Nizam" %}} (mailto:manizam@ucsc.edu)
  - {{% mention "Professor James Davis" %}} (mailto:davisje@ucsc.edu)

### Background

Recent research has shown that text-to-image models can perpetuate racial and gender stereotypes through visual output. For instance, prompts like “CEO” or “nurse” often produce racially skewed results even when no explicit race or demographic cues are provided. This project examines whether similar disparities exist **along skin tone dimensions**, focusing on **subtle biases** rather than overt stereotypes.

The key challenge is that visual bias is not always easy to measure. This project addresses this issue by utilizing **melanin-level quantification**, a continuous and interpretable proxy for skin tone, in conjunction with consistent prompt templating and multi-sample averaging to ensure statistical rigor.

---

### Objectives

- Generate datasets using consistent prompts (e.g., "A portrait of a doctor", "A homeless person", etc.)
- Use Stable Diffusion (and optionally, other models like DALL·E or Midjourney) to generate diverse image sets
- Measure bias across demographic and occupational categories using image processing tools
- Visualize the distribution of melanin values and facial features across samples
- Explore prompt-level mitigation strategies to improve fairness in output

---

### Deliverables

- Open-source codebase for prompt generation and image evaluation
- Statistical analysis of visual bias trends
- Blog post or visual explainer on findings
- Final report and recommendations on prompt engineering or model constraints

---






