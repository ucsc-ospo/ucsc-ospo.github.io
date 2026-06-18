---
title: "Building a Kubernetes-Native Support Chatbot for High-Performance Computing"
subtitle: "Introducing my NETAI project with UC OSPO"
summary: "Exploring how AI-Powered support chatbot can help researchers and students understand anomalies, diagnose issues, and respond faster with AI-assisted insights."
authors:
  - sod
tags: ["osre26", "gsoc", "ucsd", "sdsc", "kubernetes", "llm", "ai", "network diagnostics", "nrp"]
categories: ["GSoC 2026", "NETAI"]
date: 2026-06-17
lastmod: 2026-06-17
featured: true
draft: false

image:
  caption: "NRP"
  focal_point: "Center"
  preview_only: false
---

Hi! I’m {{% mention "sod" %}}, a Software Engineer with some experience in building scalable backend systems, and data-intensive services. I’m also currently pursuing a Master of Science in Information Technology at the University of the People. I'm excited to be part of UC OSPO and look forward to working with {{% mention "mfsada" %}}, John Graham, {{% mention "dweitzel" %}}, and Daniel Diaz on an AI-powered support chatbot to assist researchers and students using the [National Research Platform](https://nrp.ai/)

This summer, I’ll be working on the [NETAI](/project/osre26/ucsd/netai/) project through UC OSPO. The project focuses on developing an AI-Chatbot that integrates with NRP's LLM service to provide intelligent network diagnostics assistance, with the goal of helping researchers and students better understand complex network behavior and respond to issues more efficiently.

A major part of my work is developing a **Kubernetes-native chatbot** that connects with NRP’s managed LLM service, including models such as Qwen3-VL, GLM-4.7, and GPT-OSS. The idea is to allow network operators to ask questions in natural language, understand what is happening across the network, and receive clearer explanations of anomalies. Instead of relying only on dashboards and logs, the chatbot will help interpret telemetry, traceroute data, and performance measurements in a more accessible way.

The project involves several technical areas. I’ll be working on techniques to fine-tune LLMs using historical diagnostics data and test results so the assistant can better understand network-specific terminology and troubleshooting workflows. I’ll also be building **RESTful APIs** for chatbot interactions, refining **prompt engineering** strategies for network diagnostics, and designing responses that incorporate real-time telemetry so they stay relevant to what is happening now. On the infrastructure side, the chatbot will be deployed as Kubernetes services and will make use of GPU-enabled pods for inference.

I’m especially excited about the opportunity to combine backend engineering, cloud-native development, and AI in one project. I look forward to learning from my mentors, and to building something that can make network operations more understandable, efficient, and practical for real-world use. You can read my proposal for this project [here](https://drive.google.com/file/d/1o4P6RBsWFJbKWi30g4kaS49z8UnX--mm/view?usp=sharing).

