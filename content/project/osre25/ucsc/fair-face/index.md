---
title: "FairFace"
authors: [profjamesdavis]
author_notes: ["Professor CSE, UC Santa Cruz"]
tags: ["osre25", "UC", "reproducibility", "Fairness in AI", "Data augmentation"]
date: 2025-02-28
lastmod: 2022-02-28
---

### FairFace: Reproducible Bias Evaluation in Facial AI Models via Controlled Skin Tone Manipulation

Bias in facial AI models remains a persistent issue, particularly concerning skin tone disparities. Many studies report that AI models perform differently on lighter vs. darker skin tones, but these findings are often difficult to reproduce due to variations in datasets, model architectures, and evaluation settings.
The goal of this project is to investigate bias in facial AI models by manipulating skin tone and related properties in a controlled, reproducible manner. By leveraging BioSkin, we will adjust melanin levels and other skin properties on existing human datasets to assess whether face-based AI models (e.g., classification and vision-language models) exhibit biased behavior toward specific skin tones.


- **Topics:**  `Fairness & Bias in AI`, `Face Recognition & Vision-Language Models`, `Dataset Augmentation for Reproducibility`
- **Skills:** Machine Learning & Computer Vision, Deep Learning (PyTorch/TensorFlow), Data Augmentation & Image Processing, Reproducibility & Documentation (GitHub, Jupyter Notebooks).
- **Difficulty:** Moderate 
- **Size:** Medium or Large ( Can be completed in either 175 or 350 hours, depending on the depth of analysis and number of models tested.) 
- **Mentors:** [James Davis](mailto:davisje@ucsc.edu), [Alex Pang](mailto:pang@soe.ucsc.edu)

### Key Research Questions
1. Do AI models perform differently based on skin tone?
    * How do classification accuracy, confidence scores, and error rates change when skin tone is altered systematically?
2. What are the underlying causes of bias?
    * Is bias solely dependent on skin tone, or do other skin-related properties (e.g., texture, reflectance) contribute to model predictions?
    * Is bias driven by dataset imbalances (e.g., underrepresentation of certain skin tones)?
    * Do facial features beyond skin tone (e.g., structure, expression, pose) contribute to biased predictions?
3. Are bias trends reproducible?
    * Can we replicate bias patterns across different datasets, model architectures, and experimental setups?
    * How consistent are the findings when varying image sources and preprocessing methods?


### Specific Tasks:
1. Dataset Selection & Preprocessing
    * Choose appropriate face/human datasets (e.g., FairFace, CelebA, COCO-Human).
    * Preprocess images to ensure consistent lighting, pose, and resolution before applying transformations.
2. Skin Tone Manipulation with BioSkin
    * Systematically modify melanin levels while keeping facial features unchanged.
    * Generate multiple variations per image (lighter to darker skin tones).
3. Model Evaluation & Bias Analysis
    * Test face classification models (e.g., ResNet, FaceNet) and vision-language models (e.g., BLIP, LLaVA) on the modified images.
    * Compute fairness metrics (e.g., demographic parity, equalized odds).
4. Investigate Underlying Causes of Bias
    * Compare model behavior across different feature sets.
    * Test whether bias persists across multiple datasets and model architectures.
5. Ensure Reproducibility
    * Develop an open-source pipeline for others to replicate bias evaluations.
    * Provide codebase and detailed documentation for reproducibility.




