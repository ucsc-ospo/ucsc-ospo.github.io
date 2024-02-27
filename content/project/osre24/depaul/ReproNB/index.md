---
title: "ReproNB: Reproducibility of Interactive Notebook Systems" 
authors:
- tmalik
author_notes:
- "DePaul University "
tags: [osre24, reproducibility, HPC, MPI, "distributed systems"]
date: 2024-02-26
lastmod: 2024-02-26
---

**Project Idea Description**

- **Topics:** HPC, MPI, distributed systems 
- **Skills:** C++, Python
- **Difficulty:** Difficult
- **Size:** Large; 350 hours 
- **Mentors:** {{% mention tmalik %}} 

Notebooks have gained wide popularity in scientific computing. A notebook is both a web-based interactive front- end to program workflows and a lightweight container for sharing code and its output. Reproducing notebooks in different target environments, however, is a challenge. Notebooks do not share the computational environment in which they are executed. Consequently, despite being shareable they are often not reproducible. We have developed [FLINC](https://github.com/depaul-dice/Flinc) (see also [eScience'22 paper](https://dice.cs.depaul.edu/pdfs/pubs/C31.pdf)) to address this problem. However, it currently does not comply with all forms of experiments, especially those relating to HPC experiments. In this project we will extend FLINC to HPC experiments. This will involve using recording and replaying mechanisms such as [ReMPI](https://kento.github.io/code/) and [rr](https://rr-project.org/
) within FLINC.   

**Project Deliverable**

The project deliverable will be a set of HPC experiments that are packaged with FLINC and available on Chamaeleon. 



