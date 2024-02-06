---
title: "FSA: Benchmarking Fail-Slow Algorithms " 
authors: [Kexin Pei / Ruidan Li]
author_notes: [Assistant Professor at the University of Chicago, PhD Student at the University of Chicago]
tags: [osre24, reproducibility, "storage systems", machine learning"]
date: 2024-02-06
lastmod: 2024-02-06
---

**Project Idea Description**

In the realm of modern applications, achieving not only low but also predictable response times is a critical requirement. Performance instability, even when it amounts to just a few milliseconds of delay, can result in violations of Service Level Objectives (SLOs). Redundancy at the RAID group level provides a layer of protection; however, the early identification of potential slowdowns or failures is paramount in minimizing their impact on overall system latency.

Fail-Slow represents a unique type of fault within storage systems, characterized by the system's ability to continue functioning while progressively deteriorating – its performance significantly drops below expected levels. Notably, fail-slow conditions are responsible for a considerable share of latency tails. Detecting fail-slow faults is particularly challenging, as they can be easily masked by the normal fluctuations in performance. Consequently, the identification of fail-slow faults is a critical area of research, demanding meticulous attention.

Several strategies have been developed to address the fail-slow issue, yet the question of their broad applicability remains. We plan to implement and assess various existing fail-slow detection algorithms, examining their strengths and weaknesses. Our analysis will concentrate on key questions:

How promptly can the algorithm identify a fail-slow symptom?
What methods does the algorithm employ to accurately distinguish fail-slow incidents, thereby minimizing false negatives?
Through what approach does the algorithm achieve the right sensitivity level to keep false positives in check?

This evaluation aims to shed light on the effectiveness of current methodologies in detecting fail-slow faults, crucial for enhancing system reliability and performance.

Building upon our evaluation of several fail-slow detection algorithms, our objective is to harness advanced machine learning (ML) models to develop a novel algorithm. This initiative seeks to address and potentially compensate for the identified weaknesses in existing methodologies. By focusing on the critical aspects of early detection, accurate differentiation, and optimal sensitivity, we aim to create a solution that reduces both false negatives and false positives, thereby enhancing overall system reliability. This approach represents a strategic effort to not only advance the current state of fail-slow detection but also to contribute significantly to the resilience and performance of storage systems.


**Project Deliverable**
- A Trovi artifact for the existing Fail-Slow detection algorithms on Chameleon Cloud
- A GitHub repository containing the full evaluation result
- A Google Colab notebook for quick replay


**Topics:** Storage systems, machine learning

**Skills:** Python, PyTorch, Bash scripting, Linux, Machine Learning modeling

**Difficulty:** Hard

**Size:** Large (350 hours)

**Mentors:** [Ruidan Li](https://people.cs.uchicago.edu/~ruidanli/), Kexin Pei


