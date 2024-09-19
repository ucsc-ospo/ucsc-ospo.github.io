---
title: "Developing Trustworthy Large Language Models"
subtitle: "Towards building Responsible AI"
summary:
authors: 
  - nikhilwani
  - lgilpin
tags: ["osre24", uc]
categories: ["gsoc24", "Explainable AI(Xai)", "Responsible AI"]
date: 2024-06-14
lastmod: 2024-06-14
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hi! Thanks for stopping by.

In this first blog post of a series of three, I’d like to introduce myself, my mentor, and my project. 

My name is Nikhil. I am an ML researcher who works at the intersection of NLP, ML, and HCI. I previously worked as a Machine Learning Engineer II at [VMware](https://vmware.com/) and spent some wonderful summers interning with ML teams at [NVIDIA](https://www.nvidia.com/) and [IIT Bombay](https://www.iitb.ac.in/). I also recently graduated from the [University of Southern California (USC)](https://usc.edu/) with [honors](https://www.cs.usc.edu/academic-programs/masters/cs_ms_honors/) in Computer Science and a master's thesis. 

This year at Google Summer of Code (GSoC 24), I will be working on [developing trustworthy large language models](/project/osre24/ucsc/aiealab/). I’m very grateful to be mentored by {{% mention lgilpin %}} at the [AIEA lab, UC Santa Cruz](https://aiea-lab.github.io/). I truly admire the flexibility and ownership she allows me in pursuing my ideas independently within this project. Please feel free to peruse my accepted GSoC proposal [here](https://drive.google.com/drive/folders/16DHlcHGS7psoFXYc5q2L2-GOsLwIBXl1?usp=drive_link).

**Project:**
My project has a tangible outcome:  An open-source, end-to-end, full-stack web app with a hybrid trustworthy LLM in the backend.

This open-source web app will be a lightweight tool that not only has the ability to take diverse textual prompts and connect with several LLMs and a database but also the capability to gather qualitative and quantitative user feedback. Users will be able to see how this feedback affects the LLMs' responses and impacts its reasoning and explanations (xAI). The tool will be thoroughly tested to ensure that the unit tests are passing and there is complete code coverage. 

At the moment, we are investigating LLMs and making them more trustworthy in constraint satisfaction tasks like logical reasoning and misinformation detection tasks. However, our work has applicability in other areas of Responsible AI, such as Social Norms (toxicity detection and cultural insensitivity), Reliability (misinformation, hallucination, and inconsistency), Explainability & Reasoning (lack of interpretability, limited logical, and causal reasoning), Safety (privacy violation and violence), and Robustness (prompt attacks and distribution shifts). 

**Impact:**
 - Responsible AI research teams across industry and academia can use this as a boilerplate for their user study projects.
 - Diverse PhD students and academic researchers looking to study LLM and user interaction research will find this useful.
 - LLM alignment researchers and practitioners can find this resourceful as user feedback affects the inherent rewards model of the internal LLMs.
 - Explainable AI (xAI) researchers can find value in the explanations that this tool generates, which reveal interpretable insights into how modern LLMs think and use their memory. 
These are just a few use cases; however, there are several others that we look forward to describing in the upcoming posts. 

This was my first blog in the series of three for the UC OSPO. Stay tuned for the upcoming blogs, which will detail my progress at the halfway mark and the final one concluding my work. 

If you find this work interesting and would love to share your thoughts, I am happy to chat! :) Feel free to connect on [LinkedIn](https://www.linkedin.com/in/nikhilwani/) and mention that you are reaching out from this blog post. 

It is great to meet the UC OSPO community, and thanks for reading. Bye for now.
