---
title: Is Reproducibility Enough? Understanding the Impact of Missing Settings in Artifact Evaluation
authors: [wang.7564, yu.3053]
author_notes: ["Associate Professor, CSE, Ohio State", "Ph.D. student"]
date: 2023-02-08
lastmod: 2023-03-16
tags: [osre23, reproducibility, databases, "key-value stores", "DNN training"]
---

While Artifact Evaluation tries to ensure that the evaluation results in a paper are reproducible, it leaves one question: How about experiment settings NOT reported by the paper? Such “missing settings” may create multiple problems: 1) sometimes the artifacts simply do not work under these missing settings, creating problems when a later work needs to compare to an earlier work under these settings; 2) sometimes the artifacts do not perform well under these missing settings, which may create a bias during the evaluation; 3) to improve the artifact to work under these missing settings, sometimes one needs to re-design the system, which may change the results of the original experiments.  

In this project, we plan to understand the impact of this problem: On the necessity side, how would these missing settings affect the conclusions of the original work? On the feasibility side, how much effort does it require to carry out extensive experiments? We plan to answer these questions by reproducing prior works, running them on popular settings that are not reported by these works, and fixing problems if any.  

### Measuring Research Prototypes under Unreported Settings

**Topics:** reproducibility, databases, key-value stores, DNN training  
**Skills:** Java/Python, Linux, TPC/YCSB  
**Difficulty:** Medium  
**Size:** 350 hours  
**Mentor(s):** {{% mention wang.7564 %}}, {{% mention yu.3053 %}}  

The student will first pick one or a few systems she is interested in. Then she will first try to reproduce their reported results. If successful, she will further try to measure these systems under previously unreported settings. During the procedure, she will need to diagnose and fix any problems that may show up. Finally, she will analyze whether the original conclusions still hold under these new settings and whether fixing any problems will change the performance characteristics of the target systems.
