---
title: "The urgent need to make the value of open source visible and quantifiable to university leadership" 
authors: [admin]
tags: []
Categories: [News]
date: 2023-08-01
lastmod: 2023-08-01
featured: true
draft: false
active: true

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [ospo]
---

## A surprisingly high number

Earlier this year a colleague from UC San Diego mentioned a number: 32,000. That's the estimated number of public GitHub repositories that UC San Diego faculty and students have contributed to. This discovery is interesting in at least two ways: (1) it is an example of an intuitive metric for at least a first-order approximation of the value of open source to the university's research enterprise, and (2) even if it turns out that only a fraction of 32,000 repositories represents significant work, these repositories provide a treasure trove of data to greatly improve that approximation. I quote my colleague: 
> There is a sense that 100's of faculty and thousands of students are contributing or have contributed to open source projects. These numbers were presented in a meeting that high level leadership at UCSD participated (VCR, EVC, CTO, …) and the statement made quite a stir.  

## Software production will be regulated

It is high time for the leadership of universities to understand the value of open source to their research enterprise. Software is now so important to society and the associated threat of cybercrime so great that legislation to regulate the software industry is coming. At the forefront is the European Union with its proposed Cyber Resiliency Act (CRA) which considers declaring software hazardous and might require as early as next year a burden of documentation and certification to ensure safety of software that is well beyond the means of most open source projects. While the [Open Source Initiative](https://blog.opensource.org/convening-public-benefit-and-charitable-foundations-working-in-open-domains/), the [Linux Foundation](https://linuxfoundation.eu/cyber-resilience-act), the Eclipse Foundation (see [the excellent presentation](https://www.youtube.com/watch?v=AmsM5_5QO5A) by Eclipse Executive Director Mike Milinkovich), the [Drupal Association](https://www.drupal.org/association/blog/open-source-unity-joint-concerns-over-the-proposed-cyber-resilience-act-in-the-eu), the [Apache Software Foundation](https://news.apache.org/foundation/entry/save-open-source-the-impending-tragedy-of-the-cyber-resilience-act), and [GitHub](https://github.blog/2023-07-12-no-cyber-resilience-without-open-source-sustainability/) are among the growing number of organizations that are recognizing the impact of this proposed legislation and are actively lobbying for amendments, there is, according to Milinkovich [no engagement from universities](https://youtube.com/clip/UgkxLtjHxiGQg1wdib79Q3AsvKqTZHBUxbGg)." 

## Getting universities engaged 

I think there is a good reason for this lack of engagement: _universities have little to no data to justify engagement_. While universities employ considerable staff to carefully track fund raising, publications, student enrollments, licensing income, and all kinds of other indications of societal impact, there are little to no resources dedicated to track the role of software --  particularly open source software -- in research, reproducibility, teaching, technology transfer, and how universities engage with outside stakeholders. 

The "32,000 repositories" number of a single university campus (UC San Diego) extrapolated to all research universities is just one (and very crude) indicator that the potential impact of coming legislation like EU's CRA might be significant. As the OSPO of UC Santa Cruz, the first within the UC system, we feel an urgent responsibility for making the value of open source visible and quantifiable so that the need to engage becomes obvious. 

## Proposing the Open source Repo Browser

Luckily, the technologies to help make that a reality already exist: large repository hubs such as GitHub, GitLab, and BitBucket have query APIs for discovering public repositories. We are now working with UC San Diego on extending their repository discovery to other UC campuses towards a University of California system-wide Open source Repository Browser (UC ORB). Sophisticated measurement tools exist that can characterize these repositories, including their research topics, their dependencies, their development processes, their maturity, and their community health. We will partner with [Bitergia](https://bitergia.com/bitergia-analytics/), the market leader in these tools, to ensure that we apply state of the art from the beginning. Bitergia specializes in providing quality data about open source projects and has a ready-to-use open source platform, [CHAOSS GrimoireLab](https://chaoss.github.io/grimoirelab/). By leveraging Bitergia’s knowledge and platform, we avoid building tools for which open source solutions already exist and are enabled to focus on the interesting questions that can be answered by working with the data.  

## Virtuous Cycles of Visibility

This dataset is however only a first approximation of the set of all relevant repositories. To achieve high precision and recall, these queries would have to be continually updated as new research efforts emerge, especially in large multi-campus institutions like the University of California. Thus, we will complement this effort by creating incentives for researchers to register their repositories. One example is the OSPO UC Santa Cruz’ [Open Source Research Experience](https://ospo.ucsc.edu/osre) (OSRE) which enables researchers to register their projects with Google Summer of Code and other outreach efforts. Profiling these registered repositories will allow us to identify similar projects in the dataset for targeted promotion of OSPO programs. Thus, while the initial dataset will have imperfect precision and recall, it provides a great starting point for bootstrapping UC ORB and using incentives created by OSPO programs to achieve high precision and recall. We expect that UC ORB's success will incentivize researchers to more carefully design their repository profiles so their projects are more easily discovered. These optimizations will increase research visibility, and by extension, strengthen the impact of the UC system. We in collaboration with other UC campuses will promote UC ORB to external stakeholders such as Open Source Science (a collaboration between NumFOCUS and IBM Research who are working on mapping the landscape of open source software used in science), companies who are interested in engaging with researchers, and open source foundations who are interested in supporting new technologies.

## Reducing the burden of software regulation

UC ORB will be just one instance of valuable datasets that will be hopefully established in many other universities, not only for statistics about the value of open source software but also for university researchers to explore new ways to reduce the burden of supply chain security and software safety assurance. Whatever software regulation is going to look like in the future, there is an urgent need for society to find paths towards greater security and safety without diminishing the flow of innovation. Once the value of open source software becomes visible, universities with their outstanding research talent are in a great position to not only engage but provide valuable insights of how software should be regulated in the future.