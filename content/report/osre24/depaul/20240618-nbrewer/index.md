---
title: "Assessing the Computational Reproducibility of Jupyter Notebooks"
subtitle: "How the Confluence of My Prior Experiences Led Me to My First Dissertation Chapter"
summary: "This post explores the author's journey from replicating supercomputing experiments to developing accessible research tools with Jupyter Notebooks. It highlights how these experiences shaped her Summer of Reproducibility project proposal that focuses on the computational reproducibility of Jupyter Notebooks used in scientific contexts."
authors: [nbrewer, tmalik]
tags: ["osre24", reproducibility]
categories: [SoR]
date: 2024-06-18
lastmod: 2024-06-18
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
Like so many authors before me, my first reproducibility study and very first academic publication started with the age-old platitude, "Reproducibility is a cornerstone of the scientific method." My team and I participated in a competition to replicate the performance improvements promised by a paper presented at last year's Supercomputing conference. We weren't simply re-executing the same experiment with the same cluster; instead, we were trying to confirm that we got similar results on a different cluster with an entirely different architecture. From the very beginning, I struggled to wrap my mind around the many reasons for reproducing computational experiments, their significance, and how to prioritize them. All I knew was that there seemed to be a consensus that reproducibility is important to science and that the experience left me with more questions than answers.

Not long after that, I started a job as a research software engineer at Purdue University, where I worked heavily with Jupyter Notebooks. I used notebooks and interactive components called widgets to create a web application, which I turned into a reusable template. Our team was enthusiastic about using Jupyter Notebooks to quickly develop web applications because the tools were accessible to the laboratory researchers who ultimately needed to maintain them. I was fortunate to receive the [Better Scientific Software Fellowship](https://bssw.io/fellows/nicole-brewer) to develop tutorials to teach others how to use notebooks to turn their scientific workflows into web apps. I collected those and other resources and established the [Jupyter4Science](https://www.jupyter4.science) website, a knowledgebase and blog about Jupyter Notebooks in scientific contexts. That site aims to improve the accessibility of research data and software.

There seemed to be an important relationship between improved accessibility and reuse of research code and data and computational reproducibility, but I still had trouble articulating it. In pursuit of answers, I moved to sunny Arizona to pursue a History and Philosophy of Science degree. My research falls at the confluence of my prior experiences; I'm studying the reproducibility of scientific Jupyter Notebooks. I have learned that questions about reproducibility aren't very meaningful without considering specific aspects such as who is doing the experiment and replication, the nature of the experimental artifacts, and the context in which the experiment takes place.

I was fortunate to have found a mentor for the Summer of Reproducibility, [Tanu Malik](https://ucsc-ospo.github.io/author/tanu-malik/), who shares the philosophy that the burden of reproducibility should not solely rest on domain researchers who must develop other expertise. She and her lab have developed [FLINC](https://github.com/depaul-dice/Flinc), an application virtualization tool that improves the portability of computational notebooks. Her prior work demonstrated that FLINC provides efficient reproducibility of notebooks and takes significantly less time and space to execute and repeat notebook execution than Docker containers for the same notebooks. My work will expand the scope of this original experiment to include more notebooks to FLINC's test coverage and show robustness across even more diverse computational tasks. We expect to show that infrastructural tools like FLINC improve the success rate of automated reproducibility.

I'm grateful to both the Summer of Reproducibility program managers and my research mentor for this incredible opportunity to further my dissertation research in the context of meaningful collaboration.
