---
title: "Auditing Skin Tone Bias in Text-to-Image Models"
subtitle: "Uncovering representational harms in AI-generated imagery"
summary: A midterm blog reflecting on the progress and direction of my OSRE25 project, which investigates how models like Stable Diffusion may encode and reproduce skin tone biases in response to occupational or status-based prompts.
authors: 
  - marzia
tags: ["osre25"]
categories: []
date: 2025-07-09
lastmod: 2025-07-09
featured: false
draft: false

image:
  caption: "A collage of AI-generated faces showing subtle variation in skin tone"
  focal_point: "Center"
  preview_only: false
---

As part of the [Stable Diffusion Bias Project](/project/osre25/ucsc/sd-bias), my [proposal](https://github.com/ucsc-ospo/ucsc-ospo.github.io/blob/main/content/project/osre25/ucsc/fair-face/index.md) focuses on evaluating **bias in visual outputs of generative AI models**, particularly **skin tone bias** in Stable Diffusion.

The goal is to analyze how models render people based on prompts like “a doctor” or “a homeless person,” and whether certain prompts systematically result in lighter or darker skin tones—even when race isn’t explicitly mentioned.

---

### 🧪 What I’ve Done So Far

- Designed a prompt template covering six social categories (e.g., criminal justice, profession, socioeconomic)
- Generated image datasets using Stable Diffusion with varied seeds
- Built a preprocessing pipeline to estimate **melanin values** from generated faces
- Created early visualizations showing **distributional trends in skin tone**
- Identified early evidence of bias in prompts linked to status or wealth

---

### ⚒️ Tools and Methods

- **Stable Diffusion** for controlled image generation  
- **BioSkin pipeline** to extract melanin metrics  
- **Fitzpatrick skin type approximation** (in development as a validation method)  
- Python-based data analysis and prompt auditing  
- [openai/CLIP](https://github.com/openai/CLIP) and BLIP for optional image-text alignment scoring

---

### 🔍 What I’m Seeing

Preliminary results show that even neutral prompts like “a portrait of a professor” tend to favor lighter skin tones, while prompts such as “a manual laborer” or “a homeless person” skew toward darker tones. These trends are **not always obvious to the human eye**, which is why quantitative skin tone analysis is essential.

I'm now exploring whether prompt engineering (e.g., adding “fair,” “dark-skinned,” or “diverse” descriptors) can help mitigate these imbalances.

---

### 🚧 What’s Next

- Expand dataset to 60 prompts across 6 categories
- Incorporate alternate T2I models (Midjourney, DALL·E 3)
- Write a technical report and reproducible evaluation framework
- Submit a short paper or workshop proposal to a fairness or ethics venue

---



