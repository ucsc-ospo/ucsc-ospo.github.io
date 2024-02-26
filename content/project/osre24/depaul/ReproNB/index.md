---
title: "ReproNB:Reproducibility of Interactive Notebook Systems" 
authors:
- tmalik
author_notes:
- "DePaul University "
tags: ["osre24", "reproducibility", "HPC", "MPI","distributed systems"]
date: 2024-02-26
lastmod: 2024-02-26
---

**Project Idea Description**

- **Topics:** HPC, MPI, distributed systems 
- **Skills:** C++, Python
- **Difficulty:** Difficult
- **Size:** Large; 350 hours 
- **Mentors:** {{% mention tmalik %}} 

Notebooks have gained wide popularity in scientific computing. A notebook is both a web-based interactive front- end to program workflows and a lightweight container for sharing code and its output. Reproducing notebooks in different target environments, however, is a challenge. Notebooks do not share the computational environment in which they are executed. Consequently, despite being shareable they are often not reproducible. We have developed FLINC[1]  to address this problem. However, FLINC is currently not comply with all forms of experiments, especially those relating to HPC experiments. In this project we will extend FLINC to HPC experiments. This will involve using recording and replaying mechanisms such as ReMPI [2] and rr [3] within LFINC.   

[1] https://dice.cs.depaul.edu/pdfs/pubs/C31.pdf
[2] https://kento.github.io/code/
[3] https://rr-project.org/


**Project Deliverable**

The project deliverable will be a set of HPC experiments that are packaged with FLINC and available on Chamaeleon. 



