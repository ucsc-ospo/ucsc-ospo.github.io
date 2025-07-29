---
title: "Midway Report: LINQS - Autograder (LLM Detector)"
subtitle: "Halfway through the work!"
summary: "Midterm progress report on my GSoC'25 project with OSPO."
authors:
  - anvichip
tags: ["osre25"]
categories: ["Artificial Intelligence","Machine Learning", "LLMs"]
date: 2025-07-25
lastmod: 2025-07-25
featured: true
draft: false

---

Hello everyone, I’m Anvi Kohli and in this blog post, I’ll be sharing my journey as a GSoC contributor. 
This summer I am contributing to [LINQS Autograder](https://ucsc-ospo.github.io/project/osre25/ucsc/autograder/) 
under the mentorship of Eriq Augustine and Lucas Ellenberger. 
The goal of my project is to build a tool that can detect code generated with AI. 
You can read my proposal here: [Proposal](https://summerofcode.withgoogle.com/programs/2025/projects/jxBUpvoM).

## Project Overview

The Autograder Server is an open source project that automatically grades programming assignments in real-time. 
The project supports the autograding systems used at UC Santa Cruz. 
Due to the rise of tools like GitHub Copilot and ChatGPT, students are increasingly relying on AI to complete their coding assignments. 
This poses a problem as it becomes challenging to uphold fairness in grading and ensure that students are learning.  
Our project aims to address this issue by creating a system that provides a confidence score to indicate that a piece of code was written by an AI tool.

## Progress, Challenges & Learnings

### Exploration of existing tools and systems

My mentor, Eriq Augustine, advised me to begin with simpler methodologies before progressing to more complex ones. 
So first off, I conducted an in-depth exploration of open-source repositories that detect AI-generated code. 
By building upon existing open source solutions, we can re-use pre-built tools and train them on more varied data improving their detection capabilities. This exploration helped me gain an understanding of the current work and ongoing efforts in AI-generated code detection. 

### Method 1: Transfer Learning

While exploring existing tools and research papers, I found that transfer learning has shown promising results in the detection of AI-generated code. 
Several pre-trained models like CodeBERT have been fine-tuned on labeled datasets containing AI and human-written code, and then used to classify new samples. 
Building on this, I curated a collection of publicly available datasets that could be used for this purpose.
During this process, I noticed that open-source, relevant, and good quality datasets are limited, and they vary widely in format, language coverage, and quality. 
Some focus on a single programming language, while others span multiple languages. 
Often, these dataset also lack sufficient examples. 
By standardizing these disorganized resources, we can create a comprehensive, multi-language dataset suitable for AI code detection. 

Currently, I’m working on fine-tuning these models using the curated datasets and evaluating their effectiveness in classifying AI-generated from human written code.

### Contributing to Autograder Repository

To help me get familiar with our existing codebase and gain hands-on experience with the Go programming language, my mentor assigned me an [Open Issue](https://github.com/edulinq/autograder-server/issues/141) of the repo. 
Here is my progress on the same: [PR#194](https://github.com/edulinq/autograder-server/pull/194).

Autograder is a tool used to grade programming assignments by measuring code similarity between student submissions. 
It leverages source code plagiarism detection engines like JPlag and Dolos to analyze and compare assignments during the grading process. 
This pull request introduces the ability to pass custom arguments to these engines, allowing more control and flexibility in how similarity is calculated.

As someone with no prior experience with either contributing to open source or in coding with go, I was consistently encouraged and supported by my mentors, Lucas and Eriq, who gave me valuable guidance on writing more cleaner, and efficient code. 
This experience taught me about the importance of code quality and maintainability in production-level open-source collaborative projects.

## Learning

Over the past two months, my involvement in this project has been a period of immense growth and learning. With the constant support and guidance of my mentors - Eriq Augustine and Lucas Ellenberger, I’ve had the chance to reflect on my skills, identify areas for improvement, and actively work on them.
One of the biggest takeaways for me has been understanding the importance of writing clean, readable code - something I hadn’t fully appreciated before. 
Their guidance has not only made me a better developer but have also shaped my growth more holistically. 
I’ve started paying closer attention to deadlines, communicating more thoughtfully, and ensuring my work is both thorough and reliable.
All in all, GSoC’25 has definitely proved to be a valuable experience for me.