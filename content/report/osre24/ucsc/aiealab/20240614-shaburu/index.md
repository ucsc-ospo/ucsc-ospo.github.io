---
title: "Artificial Intelligence Explainability Accountability"
subtitle: "Benchmark Suite for Explaining failures in autograding"
summary: "develop a system that explains programming errors, from syntax to logical issues, using AI and custom drivers for consistent feedback. Key deliverables include an AI benchmark suite for education and personalized AI assistance for programming learners"
authors:
  - shaburu
  - lgilpin
tags: ["osre24", uc]
categories: ["gsoc24", "Explainable AI", "xAi", "Responsible AI"]
date: 2024-06-14
lastmod: 2024-06-14
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Shaburu aka Sarthak Chowdhary"
  focal_point: "Center"
  preview_only: false
---

Hey! I'm {{% mention shaburu %}}, and I am thrilled to share my incredible journey with the Open Source Program Office of UC Santa Cruz! Association as part of Google Summer of Code (GSoC) 2024. This experience marks a pivotal milestone in my career, offering me the chance to delve into an intriguing project while learning from the brightest minds in the open-source community. Allow me to guide you through my adventure thus far, from the nerve-wracking wait for results to the exhilarating commencement of the coding period.  

Before we start here's my [Proposal](https://drive.google.com/file/d/1BzKi0fXdqCgdK0UEG9zM56W6U5CeuyAP/view?usp=drive_link).  

## Pre-GSoC Application

I had shortlisted 3 Organizations that i was working on 

- OSPO UC Santa Cruz - Amplifying Research Impact Through Open Source
- CVAT.AI - Computer Vision Data Annotation for AI
- Emory University - Biomedical Research to Advance Medical Care

On the 1st of May, like many students eagerly anticipating the results of the Google Summer of Code (GSoC) 2024, I found myself glued to my screen, anxiously awaiting the clock to strike 11:30 PM IST. After what felt like an eternity of waiting, I finally received the email that changed everything: I had been selected for GSoC 2024 with the [Open Source Program Office of UC Santa Cruz](https://ospo.ucsc.edu)!  

The first month of GSoC, known as the community bonding period, is for establishing rapport with the people working on the  project. I researched about my mentor Dr. {{% mention lgilpin %}} and  build a good rapport with her, who is an Assistant Professor in Computer Science and Engineering and an affiliate of the Science & Justice Research Center at UC Santa Cruz. She is also a part of the AI group @ UCSC and leads the [AI Explainability and Accountability (AIEA) Lab](https://aiea-lab.github.io/). Her research focuses on the design and analysis of methods for autonomous systems to explain themselves. Her work has applications to robust decision-making, system debugging, and accountability. Her current work examines how generative models can be used in iterative XAIstress testing. She guided me through the necessary documentation and explained the Project demands and requirements in detail, which was invaluable for my project.

## Project
The project aims to build a system that is capable of taking some input which will be the student’s code and explaining them their mistakes from low level syntax errors, compilation errors to high level issues such as overloaded variables.

My [Proposal](https://drive.google.com/file/d/1BzKi0fXdqCgdK0UEG9zM56W6U5CeuyAP/view?usp=drive_link) aims to create custom novel basic questions and take it up a notch by creating custom drivers for each problem, common drivers to detect low level errors and give baseline explanations for various error cases, combining these drivers to make a robust system and use third-party open source software (like monaco code editor - the editor of the web) where necessary. Write uniform and consistent feedback/explanations for Each coding problem while covering all the possible edge cases and a pipeline which will iterate the test cases and feedbacks. This benchmark suite will be used for testing the system.

Additionally I plan on building an interface that has a roadmap from basics such as arrays, hashmaps to advanced topics such as trees, heap, backtracking along with progress bars and throws confetti on successful unit tests (important). These will be using the same benchmark suite that will be built under the hood. I will be utilizing Judge0 (open-source online code execution system) for the code execution and Monaco(open-source The Editor of the Web) as the code editor for this.

**Project goals:**

 - Project Objective: By the end of summer the software should be a
novel and robust tool for helping the community of beginner and
advanced programmers alike in learning programming by
hyper-focusing on the mistakes they make and using AI to explain to
them the how, what and why of their code. Provide clear and concise
explanations accompanied by actionable suggestions for debugging
and improvement.

 - Expected deliverables: A Robust eXplainable AI benchmark suite
which will be used extensively for the undergraduate AI courses and
possibly the Graduate courses as well. Along with anyone interested
in learning programming with the help of personalized AI.

 - Future work based on project: A beautiful Gamified interface that gets
people excited to learn programming which utilizes the above
benchmark suite would be awesome to build!

When I Started my programming journey (before ChatGPT😨) I personally encountered problems that were way above my skill set and I had no way of knowing so, which used to result in spending countless hours without proper feedback as to where I was going wrong. This project has a real impact on people in an innovative way which I wish I had access to at the start of my Programming journey, so working on it comes from a place of passion. Also this specific project will test my own understanding of programming and spending the summer solidifying it, that too under the
guidance of {{% mention lgilpin %}} is a dream come true for me.
