---
title: "From Bias to Balance: Agent-Controlled Skin Tone Representation in T2I Diffusion Models"
summary: "A lightweight inference-time framework for mitigating skin tone bias in text-to-image diffusion models through LLM-guided demographic balancing."
authors:
  - marzia-nizam
tags: ["osre25"]
categories: []
date: 2025-09-24
lastmod: 2025-09-24
featured: false
image:
  caption: "Bias correction pipeline for demographically balanced image generation."
  focal_point: "center"
  preview_only: false
draft: false
---

As part of my **OSRE 2025 project**, I worked on *From Bias to Balance: Agent-Controlled Skin Tone Representation in T2I Diffusion Models* under the mentorship of Professor James Davis.  
The project builds on my existing fairness research and evolved into a full research paper currently submitted to AAAI 2026.

---

## Project Overview

Text-to-image (T2I) diffusion models like Stable Diffusion and DALL·E have revolutionized generative AI, but they often reproduce harmful stereotypes—particularly in how they depict race and skin tone across professions. For example, prompts such as “doctor” or “CEO” overwhelmingly yield lighter-skinned faces, while prompts like “janitor” or “construction worker” show darker tones, reinforcing socioeconomic stereotypes.

Most existing fairness interventions require retraining on curated datasets, which is costly and inaccessible to most users. My project instead introduces a **lightweight inference-time framework** that operates entirely at the **prompt level**. Using a large language model (LLM), the system infers real-world demographic distributions (e.g., occupational statistics) and modifies prompts to ensure balanced skin tone representation. If the LLM lacks high-confidence data, a **uniform Fitzpatrick fallback strategy** ensures diversity across all six skin tone.

---

## Key Contributions

- **LLM-guided demographic retrieval:** An agent queries sources like labor statistics and returns structured demographic distributions.  
- **Prompt-level intervention:** The system appends skin-tone descriptors directly to prompts, requiring no retraining or model access.  
- **Fallback fairness:** When demographic data is missing, prompts are balanced across Fitzpatrick I–VI tones, ensuring equitable outputs.  
- **Evaluation pipeline:** Over 3,600 images were generated across 36 occupational and non-occupational prompts, with fairness measured via ITA-based Fitzpatrick classification:contentReference[oaicite:2]{index=2}.

---

## Results

- **Bias detection:** High-prestige professions (e.g., doctors, CEOs) showed >68% light-skinned outputs, while low-status roles skewed heavily toward darker tones.  
- **Bias correction:** Our framework reduced variance in skin tone distribution by **76.7% on average**, achieving near-uniform balance across occupations.  
- **Generalization:** The method extends naturally to **gender and age balancing**, enabling intersectional fairness without retraining.
- **Efficiency:** Adds only ~10% runtime overhead, making it deployable with existing APIs (e.g., Hugging Face, Stable Diffusion).  

---

## Reflections

This project demonstrated how **fairness can be decentralized**: rather than large corporations deciding what “fair” looks like through retraining, end users can define fairness criteria at inference time. The approach highlights a new path toward **equitable AI systems that remain accessible, transparent, and adaptable**.

Future work includes extending to multi-attribute fairness (e.g., age × gender × skin tone) and integrating fairness control into broader creative workflows.

---

## Links

- 📑 [Full Paper (AAAI 2026 submission)](https://drive.google.com/file/d/16x8ZAHhNWPFg-8SOTGp7TJhLFxohxFTq/view?usp=drive_link)  
- 📂 [Supplementary Material](https://drive.google.com/file/d/18e0wd-TjV65j5kEQJLWeASsbvQ0xFptX/view?usp=drive_link)   

---

