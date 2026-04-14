---
title: "Smart Environments – An AI System for Reproducible Custom Computing Environments"
authors: [Sam Huang, marshalp]
author_notes: ["University of Chicago", "University of Chicago"]
tags: ["osre25", "reproducibility", "machine learning", "OS"]
date: 2025-06-16
lastmod: 2025-06-16
---

Hi everyone, I'm Sam! I'm excited to be working with the Argonne National Laboratory and SoR this summer on Smart Environments. Have you ever encountered a great opensource project and wanted to run it or use it locally, only to find that it's such a headache to set up all the dependencies? Maybe your system version wasn't correct, or a piece of software was outdated, or the dependencies were incompatible with something you had already on your machine?

In comes EnvGym to save the day! We want EnvGym to be an agent that would help reproduce opensource projects by automatically setting up the environmental dependencies required to get them running. That's what I will be working on for the rest of the summer! To make EnvGym work, we will be leveraging LLM agents to tackle the problem. We will use EnvGym to read documentations, understand code structures, run commands to set up environments, and reflectively react to any errors and warnings.

To build EnvGym, I have the following to-do's in mind:
- Building a dataset that includes repos to be reproduced
- Establishing a baseline using current methods
- Implementing the actual EnvGym algorithm
- Testing EnvGym against baseline performance and iteratively improving it
- Deploying EnvGym to real-world use cases and gathering feedback

Here is the repo that we are working on:
https://github.com/EaminC/EnvGym/tree/main

More updates to come, thanks for reading!
