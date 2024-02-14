---
title: "ScaleRep: Reproducing and benchmarking scalability bugs hiding in cloud systems"
authors: [bogdanstoica, wang.7564]
author_notes: [PhD Student at the University of Chicago, Associate Professor at the Ohio State University]
tags: [osre24, reproducibility, distributed systems, bug analysis]
date: 2024-02-10
lastmod: 2024-02-10
---

**Topics:** Distributed systems, Scalability, Bug analysis, Bug reproducibility  
**Skills:** Java, Python, bash scripting, perf, Linux internals  
**Difficulty:** Hard  
**Size:** Large (350 hours)  
**Mentors:** **{{% mention bogdanstoica %}} (contact person)**, {{% mention wang.7564 %}}  

**Project Idea Description**

Large-scale distributed systems are integral to the infrastructure of a wide range of applications and services. 
The continuous evolution of these systems requires ongoing efforts to address inherent faults which span a variety of issues including availability, consistency, concurrency, configuration, durability, error-handling, integrity, performance, and security. 
Recent developments in the field and the rise of cloud computing have been marked by a notable increase in the scale at which such systems operate.

This increase in scale introduces specific challenges, particularly in terms of system reliability and performance. 
As distributed systems expand beyond single machines, addressing the growing demands for computation, memory and storage becomes more difficult. 
This underlying complexity leads to the emergence of scalability bugs — defects that surface in large-scale deployments, yet do not reveal themselves in a small-scale setting.
To better understand scalability bugs, we set out to investigate a set of scalability issues documented over the last 5 years from 10 popular open-source large-scale systems. 
These bugs have led to significant operational challenges, such as system downtime, reduced responsiveness, data loss, and data corruption. 
Moreover, addressing them required extensive collaboration and problem-solving efforts among engineers and bug reporters, with discussions often spanning a month or more.

We observed that traditional bug finding techniques are insufficient for detecting scalability bugs since these defects are triggered by a mixture of scale-related aspects not properly investigated by previous approaches. 
These characteristics include the number of components involved, the system load and workload size, the reliability of recovery protocols, and the magnitude of intermediate failures. 
Although previous research examined some of these aspects, it has typically done so either in isolation (individually), or without providing a comprehensive understanding of the fundamental bug patterns, symptoms, root causes, fixes, and, more importantly, how easily these bugs can be reproduced in-house.

Therefore, the main goal of this project is to systematically understand, characterize, and document the challenges associated with scalability bugs, at-large. 
Our approach is twofold: first, to analyze scalability bugs in terms of reproducibility, and second, to develop methodologies for triggering them and measuring their impact. 
Specifically, we aim to:
1. Provide detailed accounts of bug reproduction experiences for a diverse set of recently reported scalability bugs from our benchmark applications;
2. Identify specific challenges that prevent engineers from reproducing certain scalability bugs and investigate how prevalent these obstacles are;
3. Create a suite of protocols to effectively trigger and quantify the impact of scalability bugs, facilitating their investigation in smaller-scale environments.

**Project Deliverable**

- A set of Trovi replayable artifacts enabling other researchers to easily reproduce scalability bugs for our benchmark applications.
- A set of Jupyter notebook scripts allowing for conveniently replaying each step.
- A detailed breakdown of the challenges faced when reproducing scalability bugs and how these obstacles differ from those related to more “traditional” bugs.


