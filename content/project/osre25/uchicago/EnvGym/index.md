---
title: "Smart Environments – An AI System for Reproducible Custom Computing Environments"
authors: [marshalp, YimingCheng]
author_notes: ["University of Chicago", "University of Chicago"]
tags: ["osre25", "reproducibility", "machine learning", "OS"]
date: 2025-02-18
lastmod: 2025-02-18
---

## Overview

The complexity of environment setup and the expertise required to configure specialized software stacks can often hinder efforts to reproduce important scientific achievements in HPC and systems studies. Researchers often struggle with incomplete or ambiguous artifact descriptions that make assumptions about "common knowledge" that is actually specific domain expertise. When trying to reproduce experiments, reviewers may spend excessive time debugging environment inconsistencies rather than evaluating the actual research. These challenges are compounded when experiments need to run on different hardware configurations.

This project seeks to address these fundamental reproducibility barriers by using AI to translate natural language environment requirements often used in papers or artifact descriptions into actionable, reproducible configurations—bridging the knowledge gap between experiment authors and reviewers while standardizing environment creation across different hardware platforms. We will develop an AI-driven system that automatically generates and configures reproducible computing environments based on artifact descriptions from conferences, Trovi artifacts on the [Chameleon](chameleoncloud.org) testbed, and other reliable sources for scientific experiment code and associated documentation. Leveraging Natural Language Processing (NLP), the system will allow researchers to describe desired environments in plain English, then map those descriptions onto predefined configuration templates. By simplifying environment creation and ensuring reproducibility, the system promises to eliminate duplicate setup efforts, accelerate research workflows, and promote consistent experimentation practices across diverse hardware.

## Key Outcomes

- Working Prototype: A system that automatically generates machine images deployable on bare metal and VM instances, based on user-provided requirements.
- Comprehensive Documentation: Detailed user manuals, guides, and best practices tailored to researchers, ensuring a smooth adoption process.
- Live Demo: A demonstration environment (e.g., a web app or Jupyter notebook) that shows how to request, configure, and launch reproducible cloud environments on both hardware profiles.
- Long-Term Impact: Building blocks for future AI-driven automation of cloud infrastructure, reducing human error and enabling fast, repeatable research pipelines.

**Topics**: Reproducibility, AI & NLP, Cloud Computing, DevOps and Automation

**Skills**:

- Machine Learning / AI: Familiarity with NLP methods to interpret user requirements.
- Python: Primary language for backend services and cloud interactions.
- Cloud API Integration: Experience with OpenStack or similar APIs to provision and configure images on both bare metal and virtual machines.
- DevOps: Automated environment configuration, CI/CD workflows, and containerization.

**Difficulty**: Hard

**Size**: Large

**Mentors**: {{% mention marshalp %}}

**Tasks**:

- Requirement Gathering & NLP Design
  - Research the specific needs of researchers building experimental setups.
  - Design an NLP pipeline to parse plain-English descriptions (e.g., “I need Python 3.9, CUDA 11, and scikit-learn”) into environment “recipes.”
- Backend Environment Builder
  - Implement logic that converts parsed user requirements into machine-image definitions for bare metal and VM instances.
  - Integrate with Chameleon’s APIs to provision servers, install software, and run configuration validation automatically.
- Front-End & User Experience
  - Develop an intuitive web or CLI interface that researchers can use to capture experiment environment requirements.
  - Provide real-time status updates during environment setup, along with meaningful error messages and quick-start templates.
- Testing & Validation
  - Conduct end-to-end tests using diverse software stacks (e.g., HPC libraries, machine learning frameworks) on bare metal and VM instances.
  - Ensure reproducibility by re-creating the same environment multiple times and comparing configurations.
- Documentation & Demonstration
  - Produce user-facing documentation, including tutorials and best practices for researchers who frequently run experiments on Chameleon Cloud.
  - Create a short live demo or screencast showcasing how to configure an environment for a specific research workflow.
