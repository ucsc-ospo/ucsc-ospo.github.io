---
title: "Extensions to the Scenic Driving Domain"
subtitle: "An introduction to the project and myself!"
summary: "A brief blog about what Scenic is, current issues, and end goals."
authors: 
  - aprabou
tags: ["osre26", "gsoc", "probabilistic programming", "scenario specification", "uc", "simulation", "scenic"]
categories: ["GSoC 2026" , "Scenic", "Open Source"]
date: 2026-05-05
lastmod: 2026-05-05
featured: true
draft: false

image:
  focal_point: "Center"
  preview_only: false
---

# Scenic: Extensions to the Scenic Driving Domain (GSoC '26)

Hi! I'm [Ashwin](https://linkedin.com/in/aprabou), and I'm excited to be a part of UC OSPO and look foward to working on Scenic alongside [Daniel Fremont](https://ucsc-ospo.github.io/author/daniel-fremont/) and [Eric Vin](https://ucsc-ospo.github.io/author/eric-vin/) for Google Summer of Code 2026!

## About Myself
I'm a computer science student at UC Santa Cruz, and I love to build and learn. I regularly compete in hackathons and challenges, and in my free time I tinker with new technologies.

## What is Scenic?
Scenic is a programming language used to test systems like self-driving cars by automatically creating large numbers of realistic driving scenarios. Instead of manually designing every test, you describe a general situation—like cars at an intersection or a pedestrian crossing—and Scenic generates many variations using controlled randomness. It works with road map files such as OpenDRIVE, which define lanes, roads, and traffic signals, and turns them into usable objects so you can easily place cars, pedestrians, and events in a scene. This allows engineers to generate diverse test cases and verify whether autonomous systems behave safely across real-world conditions.

## Current Issues
While the driving domain is powerful, it has several limitations that hinder real-world usage, including failures on certain OpenDRIVE maps, inaccuracies when following curved roads, missing semantic road information, and the lack of connections between traffic signals and the lanes they control.

## Goals
My proposal addresses these limitations. Over the summer, I will focus on improving the robustness of Scenic and implementing features such as more accurate road-following using a Frenet-frame coordinate system, better distance and time-to-collision calculations based on road geometry, extraction of semantic road metadata like speed limits and road types, traffic signal–lane linkage to enable realistic behaviors like stopping at red lights, and modular, reusable driving scenarios for building more complex simulations.



I look forward to learning a lot this summer and sharing my progress along the way!

