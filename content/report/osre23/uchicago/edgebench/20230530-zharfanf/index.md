---
title: "Reproduce and benchmark self-adaptive edge applications under dynamic resource management"
subtitle: ""
summary: ""
authors: [zharfanf]
author_notes: ["A computer networking enthusiast from ITB"]
tags: ["osre23"]
categories: [SoR]
date: 2023-05-30
lastmod: 2023-06-10
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

Hello there!

I am Faishal Zharfan, a senior year student studying Telecommunication Engineering at Bandung Institute of Technology (ITB) in Bandung, Indonesia, my [proposal](https://drive.google.com/file/d/1u3UsCQZ40erpPmyoyn8DEVqH5Txmvvkz/view?usp=drive_link). I'm currently part of the [Edgebench](https://ospo.ucsc.edu/project/osre23/uchicago/edgebench/) under the mentorship of {{% Yuyang Huang %}}. The main goal of this project is to be able to reproduce and benchmark self-adaptive video applications using the proposed solution.

The topic that I'm currently working on is "Reproduce and benchmark self-adaptive edge applications under dynamic resource management" or known as edgebench is led by Prof. Junchen Jiang and Yuyang Huang. Edgebench is a project that focuses on how to efficiently distribute resource (bandwidth and cpu usage) across several video applications. Nowaday's video applications process its data or video on a server or known as edge computing, hence bandwidth or compute unit may be the greatest concern if we talk about edge computing in terms of WAN, because it is strictly limited. We may distribute the bandwidth evenly across the cameras, however the needs of bandwidth/compute unit of each camera is different. Therefore we need another solution to tackle this problem, the solution proposed recently is called "accuracy gradient", with this solution, we can tell how much of one application needs the bandwidth on a certain time to achieve higher accuracy. The goal of this solution is to allocate more bandwidth to the apps which has the higher f1-score improvement and reduce the other which doesn't have a significant diminishment of f1-score. Henceforth, in the end we would have a higher total f1-score.

Throughout this summer, we have planned to implement the "accuracy gradient" and test several baselines to be compared with the solution. As for the implementation, we are currently implementing the latency measurement. We are aware that there is an overhead over this solution, therefore the latency should be taken into account.