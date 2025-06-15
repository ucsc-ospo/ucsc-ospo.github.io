---
title: "Introducing Scenic-RoboSuite Interface"
subtitle: "Extending Scenic with new simulators"
summary: "Initial report on Scenic-RoboSuite integration. Coding phase: Week 3. status: Basic Skeleton Implementation of the interface is made, Scenic to Robosuite bridge is achived, basic examples and test sets made"
authors: 
  - sahil-tgs
tags: ["osre25", "gsoc", "robotics", "probabilistic programming", "scenario specification", "uc", "simulation", "mujoco", "scenic"]
categories: ["GSoC 2025", "Robotics", "Open Source"]
date: 2025-06-15
lastmod: 2025-06-15
featured: true
draft: false

image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hey! I'm [Sahil](https://sahiltgs.super.site/), working on integrating Scenic with RoboSuite for GSoC 2025. My [project](https://sahiltgs.super.site/gsoc/uc-ospo-proposal) is mentored by [Daniel Fremont](https://ucsc-ospo.github.io/author/daniel-fremont/) and [Eric Vin](https://ucsc-ospo.github.io/author/eric-vin/) .


I'm connecting [Scenic](https://scenic-lang.org/) (a probabilistic programming language for scenarios) with [RoboSuite](https://robosuite.ai/) (a robotics simulation framework). Basically, you write simple scenario descriptions and get complex 3D robot simulations automatically.

Currently, as I'm building things and learning how Scenic works, I have been able to get the basic skeleton for the simulator interface working. I've implemented the simulator class and built a world model that can translate Scenic objects into RoboSuite's simulator (which is MuJoCo-based). The interface now handles precise object placement in the world pretty well.

One of the trickier parts was figuring out the translation logic between Scenic and RoboSuite. I managed to overcome this by building a system that automatically detects the shape of objects when moving between the two frameworks, which lays a foundation for more complex object mapping later on.

I've also built some basic example scenarios to run and test with. Currently working on more complex examples and testing Scenic's features like probabilistic object placement, constraint satisfaction, and spatial relationships between objects.

In summary, the "Scenic to RoboSuite" part of the interface is pretty much done. For next week, I need to work on the "RoboSuite to Scenic" part - basically getting feedback and state information flowing back from the simulation. Achieving this will make a complete bridge and give us a working simulator interface, which is the first major milestone for the project.
