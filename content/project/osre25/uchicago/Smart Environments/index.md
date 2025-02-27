---
title: "Smart Environments – An AI System for Reproducible Custom Computing Environments" 
authors: [mpowers, msherman]
author_notes: ["University of Chicago", "University of Chicago"]
tags: ["osre25", "reproducibility", "machine learning", "OS"]
date: 2025-02-18
lastmod: 2025-02-18
---

## Overview

Modern research on cloud testbeds often requires setting up specialized software environments on both virtual machines (VMs) and bare metal servers. This can be tedious and prone to error if performed manually—especially when researchers need to replicate the same environment across different hardware configurations. This project aims to address these challenges by developing an AI-driven system that automatically generates and configures reproducible computing environments on the [Chameleon Cloud](chameleoncloud.org) testbed. Leveraging Natural Language Processing (NLP), the system will allow researchers to describe desired environments in plain English, then map those descriptions onto predefined configuration templates. By simplifying environment creation and ensuring reproducibility, the system promises to eliminate duplicate setup efforts, accelerate research workflows, and promote consistent experimentation practices across diverse hardware.

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
**Mentors**: Marc Richardson (mtrichardson@uchicago.edu)
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
