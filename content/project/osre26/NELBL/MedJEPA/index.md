---
title: "MedJEPA: Self-Supervised Medical Image Representation Learning with JEPA"
authors: [bindong,LinseyPang]
author_notes: ["Research Scientist, Lawrence Berkeley Lab","Northeastern"]
tags: ["osre26", "uc", "AI", "LLM", "Health"]
date: 2026-01-19T10:15:56-07:00
lastmod: 2026-01-19T10:15:56-07:00
---

###  Project Description
[MedJEPA] Medical image analysis is fundamental to modern healthcare, enabling disease diagnosis, treatment planning, and patient monitoring across diverse clinical applications. In radiology and pathology, deep learning models support automated detection of abnormalities, tumor segmentation, and diagnostic assistance. Medical imaging modalities including X-rays, CT scans, MRI, ultrasound, and histopathology slides generate vast amounts of unlabeled data that could benefit from self-supervised representation learning. Clinical applications include cancer detection and staging, cardiovascular disease assessment, neurological disorder diagnosis, and infectious disease screening. In drug discovery and clinical research, analyzing medical images helps evaluate treatment efficacy, predict patient outcomes, and identify biomarkers for disease progression. Telemedicine and point-of-care diagnostics benefit from AI-powered image analysis that extends expert-level interpretation to underserved regions. However, medical imaging faces unique challenges: limited labeled datasets due to expensive expert annotation, patient privacy concerns restricting data sharing, domain shift across different imaging equipment and protocols, and the need for models that generalize across hospitals and populations.
Traditional medical image analysis relies heavily on supervised learning with manually annotated labels, creating bottlenecks due to the scarcity and cost of expert annotations. Existing self-supervised methods applied to medical imaging often employ complex training procedures with numerous heuristics—momentum encoders, stop-gradients, teacher-student architectures, and carefully tuned augmentation strategies—that may not translate well across different medical imaging modalities and clinical contexts. These approaches struggle with domain-specific challenges such as subtle pathological features, high-resolution images, 3D volumetric data, and the need for interpretable representations that clinicians can trust. To address these challenges, we propose MedicalJEPA: Self-Supervised Medical Image Representation Learning with Joint-Embedding Predictive Architecture, which leverages the theoretically grounded LeJEPA framework for 2D medical images and V-JEPA principles for medical video and volumetric data, creating a unified, scalable, and heuristics-free approach specifically tailored for medical imaging applications.
By utilizing the principled JEPA frameworks with objectives like Sketched Isotropic Gaussian Regularization (SIGReg), MedJEPA eliminates complex training heuristics while learning clinically meaningful representations from unlabeled medical images. Unlike conventional self-supervised methods that require extensive hyperparameter tuning and may not generalize across medical imaging modalities, MedicalJEPA provides a clean, theoretically motivated framework with minimal hyperparameters that adapts to diverse medical imaging contexts—from chest X-rays to histopathology slides to cardiac MRI sequences. The learned representations can support downstream tasks including disease classification, lesion detection, organ segmentation, and survival prediction, while requiring significantly fewer labeled examples for fine-tuning. This approach democratizes access to state-of-the-art medical AI by enabling effective learning from the vast amounts of unlabeled medical imaging data available in hospital archives, addressing the annotation bottleneck that has limited progress in medical AI.




### Project Objectives
Aligned with the vision of the 2026 Open Source Research Experience (OSRE), this project aims to apply Joint-Embedding Predictive Architecture (JEPA) frameworks to medical image representation learning, addressing the critical challenge of learning from limited labeled medical data. Medical imaging generates enormous amounts of unlabeled data, but supervised learning approaches are bottlenecked by the scarcity and cost of expert annotations. Existing self-supervised methods often rely on complex heuristics that don't generalize well across diverse medical imaging modalities, equipment vendors, and clinical protocols.
This project will leverage the theoretically grounded LeJEPA framework for 2D medical images (X-rays, histopathology slides, fundus images) and V-JEPA principles for temporal and volumetric medical data (cardiac MRI sequences, CT scans, surgical videos). The core challenge lies in adapting these heuristics-free, stable frameworks to medical imaging's unique characteristics: subtle pathological features requiring fine-grained representations, high-resolution images demanding efficient processing, domain shift across hospitals and equipment, and the need for interpretable features that support clinical decision-making. The learned representations will be evaluated on diverse downstream clinical tasks including disease classification, lesion detection, organ segmentation, and prognosis prediction, with emphasis on few-shot learning scenarios that reflect real-world annotation constraints. Below is an outline of the methodologies and models that will be developed in this project.
 

- **Step 1: Medical Data Preparation**: 
Develop data processing pipelines for diverse medical imaging modalities, implementing DICOM/NIfTI parsing, standardized preprocessing, and efficient data loading for self-supervised pre-training.
Prepare 2D medical image datasets:
Chest X-rays: ChestX-ray14, MIMIC-CXR, CheXpert for lung disease detection
Histopathology: Camelyon16/17 (breast cancer), PCam (patch-level classification)
Retinal imaging: EyePACS, APTOS (diabetic retinopathy), Messidor
Dermatology: HAM10000, ISIC (skin lesion classification)
Prepare 3D volumetric and temporal medical data:
CT scans: LIDC-IDRI (lung nodules), Medical Segmentation Decathlon datasets
MRI sequences: BraTS (brain tumors), ACDC (cardiac MRI), UK Biobank cardiac videos
Medical video: Surgical procedure videos, endoscopy recordings, ultrasound sequences
Implement medical imaging-specific preprocessing: intensity normalization, resolution standardization, handling of multi-channel medical images (different MRI sequences, RGB histopathology), and privacy-preserving anonymization.
Design masking strategies appropriate for medical imaging: spatial masking for 2D images, volumetric masking for 3D scans, temporal masking for sequences, and anatomy-aware masking that respects organ boundaries.
Create data loaders supporting high-resolution medical images, 3D volumes, and multi-modal inputs (e.g., multiple MRI sequences).




- **Step 2: JEPA Model Implementation for Medical Imaging**: 
Implement LeJEPA for 2D medical images:
Adapt joint-embedding predictive architecture for medical image characteristics (high resolution, subtle features, domain-specific patterns)
Apply Sketched Isotropic Gaussian Regularization (SIGReg) to learn clinically meaningful embedding distributions
Maintain single trade-off hyperparameter and heuristics-free training for reproducibility across medical imaging centers
Support various encoder architectures: Vision Transformers for global context, ConvNets for local features, hybrid approaches
Extend to V-JEPA for medical video and volumetric data:
Spatiotemporal encoding for cardiac MRI sequences, surgical videos, and time-series medical imaging
Temporal prediction objectives for understanding disease progression and treatment response
3D volume processing for CT and MRI scans with efficient memory management
Multi-slice and multi-sequence learning for comprehensive medical imaging contexts
Develop medical domain-specific enhancements:
Multi-scale representation learning to capture both fine-grained pathological details and global anatomical context
Interpretability mechanisms: attention visualization, feature attribution, and embedding space analysis for clinical validation
Robustness to domain shift: training strategies that generalize across different scanners, protocols, and institutions
Privacy-preserving training considerations compatible with medical data regulations (HIPAA, GDPR)
Implement efficient training infrastructure:
Support for distributed training across multiple GPUs for large medical imaging datasets
Memory-efficient processing of high-resolution images and 3D volumes
Checkpoint management and model versioning for clinical deployment pipelines
Minimal-code implementation (≈50-100 lines) demonstrating framework simplicity



- **Step 3: Evaluation & Safety Validation**: :
Disease Classification Tasks:
Multi-label chest X-ray classification: 14 pathology classes on ChestX-ray14, MIMIC-CXR
Diabetic retinopathy grading: 5-class classification on EyePACS, APTOS
Skin lesion classification: 7-class classification on HAM10000
Brain tumor classification: glioma grading on BraTS dataset
Evaluate with linear probing, few-shot learning (5-shot, 10-shot), and full fine-tuning
Lesion Detection and Segmentation:
Lung nodule detection on LIDC-IDRI dataset
Tumor segmentation on Medical Segmentation Decathlon tasks
Polyp detection in colonoscopy videos
Cardiac structure segmentation in MRI sequences
Clinical Prediction Tasks:
Survival prediction from histopathology slides
Disease progression prediction from longitudinal imaging
Treatment response assessment from pre/post imaging pairs
Few-Shot and Low-Data Regime Evaluation:
Systematic evaluation with 1%, 5%, 10%, 25%, 50% of labeled training data
Comparison against supervised baselines and ImageNet pre-training
Analysis of annotation efficiency: performance vs. number of labeled examples required



### Project Deliverables
This project will deliver three components: software implementation,  clinical evaluation, and practical deployment resources. The software implementing MedicalJEPA will be hosted on GitHub as an open-access repository with modular code supporting multiple medical imaging modalities (2D images, 3D volumes, videos), pre-trained model checkpoints on major medical imaging datasets (chest X-rays, histopathology, MRI), training and evaluation scripts with medical imaging-specific preprocessing pipelines, privacy-preserving training implementations compatible with clinical data regulations, and comprehensive documentation including tutorials for medical AI researchers and clinicians. The evaluation results will include benchmarks on 10+ medical imaging datasets across diverse modalities and clinical tasks, few-shot learning analysis demonstrating annotation efficiency gains, cross-institutional validation studies showing robustness to domain shift, interpretability visualizations enabling clinical validation of learned representations, and detailed comparisons against supervised baselines and existing medical self-supervised methods. .

### NeuroHealth

- **Topics**:  Self-Supervised Medical Image Representation Learning with JEPA
- **Skills**: Proficiency in Python, Pytorch, Github, JEPA
- **Difficulty**: Difficult
- **Size**: Large (350 hours)
- **Mentor**: {{% mention bindong %}}, {{% mention LinseyPang %}}

### References: 

- LeJEPA: Provable and Scalable Self-Supervised Learning Without the Heuristics - Randall Balestriero and Yann LeCun, arXiv 2024
- Revisiting Feature Prediction for Learning Visual Representations from Video (V-JEPA) - Adrien Bardes et al., arXiv 2024
- Self-Supervised Learning from Images with a Joint-Embedding Predictive Architecture - Mahmoud Assran et al., CVPR 2023 (I-JEPA)
- ChestX-ray14: Hospital-Scale Chest X-Ray Database - https://nihcc.app.box.com/v/ChestXray-NIHCC
- Medical Segmentation Decathlon - http://medicaldecathlon.com/
- MIMIC-CXR Database - https://physionet.org/content/mimic-cxr/
- The Cancer Imaging Archive (TCIA) - https://www.cancerimagingarchive.net/
- UK Biobank Imaging Study - https://www.ukbiobank.ac.uk/enable-your-research/about-our-data/imaging-data



