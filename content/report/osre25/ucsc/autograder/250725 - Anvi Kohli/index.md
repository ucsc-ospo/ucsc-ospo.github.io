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
Hello everyone, I’m Anvi Kohli. In this blog post, I’ll be sharing my journey as a contributor in GSoC with my project — 'LINQS: Autograder'. The goal of my project is to build a tool that can detect code generated with AI. You can find more information about the project here: [Autograder](https://ucsc-ospo.github.io/project/osre25/ucsc/autograder/), and read my proposal here: [Proposal](https://summerofcode.withgoogle.com/programs/2025/projects/jxBUpvoM).


## Project Overview

Autograder is an open source tool used by UCSC to grade programming assignments. Due to the rise of AI tools like GitHub Co-pilot and ChatGPT, students are increasingly relying on these AI tools for completion their coursework. This poses a problem as it becomes challenging to uphold fairness in grading and ensure that students are learning.  
Autograder aims to address this issue by creating a system that provides a confidence score to indicate that a piece of code was written by an AI tool.

## Progress, Challenges & Learnings

### Exploration of existing tools and systems

My mentor, Eriq Augustine, advised me to begin with simpler methodologies before progressing to more complex ones. So first off, I conducted an in-depth exploration of open-source repositories related to use cases similar to ours. The goal was to avoid reinventing the wheel by building upon existing solutions rather than starting from scratch.

- Challenges: There were only a limited number of active and relevant open-source repositories available, which made the search more difficult.
- Learnings: This process helped me gain an understanding of the current work which has been done for detecting AI-generated code.

### Datasets and Model Training

While exploring existing tools and research papers, I found that transfer learning has shown promising results in the detection of AI-generated code. Several pre-trained models have been fine-tuned on labeled datasets containing AI and human-written code, and then used to classify new samples. Building on this, I curated a collection of publicly available datasets that could be used for this purpose.

Currently, I’m working on fine-tuning these models using the curated datasets and evaluating their effectiveness in classifying AI-generated from human written code.

- Challenges: High-quality datasets with sufficient examples are limited and often not well-maintained.
- Learnings: Revisited core machine learning concepts, especially classification algorithms like Random Forest, SVM, and XGBoost etc.


### Contributing to Autograder Repository

To help me get familiar with our existing codebase and gain hands-on experience with the Go programming language, my mentor assigned me an [Open Issue](https://github.com/edulinq/autograder-server/issues/141) of the repo. Here is my progress on the same: [PR#194](https://github.com/edulinq/autograder-server/pull/194).
Our autograder uses the JPlag and Dolos engine in the grading processes, the PR aims to implement a functionality to pass custom engine options for these engines. 

- Challenges: I had no prior experience with open-source contributions or the Go language. Thankfully, my mentors, Lucas and Eriq, were incredibly supportive and consistently encouraged me to improve.
- Learnings: I received valuable guidance on writing cleaner, more efficient, and readable code. This experience taught me the importance of code quality and maintainability in collaborative projects.


## Learning

Over the past two months, my involvement in this project has been a period of immense growth and learning. With the support and guidance of my mentors - Eriq Augustine and Lucas Ellenberger, I’ve had the chance to reflect on my skills, identify areas for improvement, and actively work on them. I'm grateful to my mentors for their guidance — their insights have not only made me a better developer but have also shaped my growth more holistically. GSoC’25 has definitely proved to be a valuable experience for me.

