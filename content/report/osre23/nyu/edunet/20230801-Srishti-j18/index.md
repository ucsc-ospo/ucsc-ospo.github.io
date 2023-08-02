---
title: "Mid-term blog post for Teaching Computer Networks with Reproducible Research: Developing a 'classroom competition' for adaptive video delivery"
subtitle: "" 
authors: [Srishti-j18]
tags: ["osre23", reproducibility]
categories: ["SummerofReproducibility23"]
date: 2023-08-01
lastmod: 2023-08-01
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

Hello! 

I am Srishti Jaiswal and this is my second blog post for the 2023 Summer of Reproducibility Fellowship.

## Introduction

As I reach the halfway mark of my internship journey, I have had the incredible opportunity to work on a project that revolves around reproducing an adaptive video research result using cloud-based experimentation. This blog post delves into my exciting work so far, the significant milestones achieved, specific accomplishments to celebrate, and the challenges overcome. Utilizing CloudLab and FABRIC, I embarked on a journey to reproduce essential figures from the research paper [Downton Abbey Without the Hiccups: Buffer-Based Rate Adaptation for HTTP Video Streaming](https://drive.google.com/file/d/1WehSLII0Werh45Nk8KUgQBCQ9IEn2K-r/view?usp=sharing), ensure Python2 and Python3 compatibility and incorporate an Estimated Download Rate column in the log file produced by the video client. Let's explore the details of this captivating internship experience.

## Major Milestones Reached

Here are the milestones we have reached so far:

1. Familiar with CloudLab and Fabric Testbeds: I learned how to run an adaptive video experiment, which is the jumping-off point for my project, on the CloudLab and FABRIC platforms.

2. Python2 and Python3 Compatibility: My first task was to port an existing open-source code base developed for Python2 (which is no longer supported) so that it can run in Python3.
Now code is running successfully in both versions for all the policies of the existing open source, i.e. Basic, Netflix and Sara. 
Fixed [issue#1](https://github.com/Srishti-j18/AStream/issues/1) .

3. Estimated Download Rate for Basic Policy: To make it easier for users to understand and visualize how the adaptive video policy works, I added an additional metric, “Estimated Download Rate”, to the output file produced by the adaptive video client.

4. Graphing Buffer Occupancy and Estimated Download Rate: I extended the existing experiment to show two additional visualizations that are important for understanding how the adaptive video client works: buffer occupancy vs time and estimated download rate vs time.

## Overcoming Challenges

I encountered several challenges throughout this project, especially as it was my first time working independently on a research paper as a third-year engineering student. However, with my mentor's guidance and support, I persevered and learned to tackle each obstacle with determination.

One significant challenge was porting the entire code from Python2 to Python3. This transition resulted in numerous errors, and I often found it challenging to pinpoint where the mistakes occurred. To overcome this, I adopted a step-by-step approach, fixing errors one by one and verifying them using Python2 for comparison.

Understanding the complex codebase was another hurdle that led to moments of feeling stuck in an infinite loop. But every time I faced such situations, I sought my mentor's advice, and together, we made strategic changes to overcome these challenges.

I am immensely grateful for my mentor's expertise and support throughout this internship. Her guidance played a crucial role in helping me navigate through the challenges and grow both professionally and personally. I eagerly look forward to the rest of the journey, knowing that I can continue making meaningful contributions to this research project with her inspiring mentorship.

## Future Prospects

As the second half of my internship approaches, I am eager to refine further and expand our experimentation.
Our main aim is to reproduce the existing work and provide a clear guide for other students to do the same for this, I have to create a framework that helps them improve and build upon this work. 

I hope you enjoyed reading this blog post.If you have any questions or feedback, please feel free to contact me. Thank you for your attention and stay tuned for more updates!
