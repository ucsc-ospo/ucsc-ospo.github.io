---
title: "Scenic: A Language for Design and Verification of Autonomous Cyber-Physical Systems"
authors: [dfremont]
author_notes: ["Associate Professor, Computer Science and Engineering, UC Santa Cruz"]
tags: ["osre26", "uc", "ai", "ml", "formal methods", "probabilistic programming"]
date: 2026-01-24
lastmod: 2026-01-24
---

[Scenic](https://scenic-lang.org/) is a probabilistic programming language for the design and verification of autonomous cyber-physical systems like self-driving cars.
Scenic allows users to define *scenarios* for testing or training their system by putting a probability distribution on the system's environment: the positions, orientations, and other properties of objects and agents, as well as their behaviors over time.
Sampling these scenarios and running them in a simulator yields synthetic data which can be used to train or test a system.
Since Scenic was released open-source in 2019, our group and many others in academia have used Scenic to find, diagnose, and fix bugs in autonomous cars, aircraft, robots, and other kinds of systems.
In industry, it is being used by companies including Boeing, Meta, Deutsche Bahn, and Toyota in domains spanning autonomous driving, aviation, household robotics, railways, maritime, and virtual reality.

Our long-term goal is for Scenic to become a widely-used common representation and toolkit supporting the entire design lifecycle of AI-based cyber-physical systems.
Towards this end, we have many summer projects available, ranging from adding new application domains to working on the Scenic compiler and sampler:

1. Extensions to the Scenic driving domain
2. Interfacing Scenic to new simulators
3. Scenic distribution visualizer

See the sections below for details.

### Extensions to the Scenic Driving Domain

 - **Topics:** `Autonomous Driving` `3D modeling`
 - **Skills:** Python; basic vector geometry
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** {{% mention "dfremont" %}}, {{% mention "evin" %}}

Scenic scenarios written to test autonomous vehicles use the [driving domain](https://docs.scenic-lang.org/en/latest/modules/scenic.domains.driving.html), a Scenic library defining driving-specific concepts including cars, pedestrians, roads, lanes, and intersections.
The library extracts information about road networks, such as the shapes of lanes, from files in the standard [OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) format.

There are several potential goals of this project, including:
- Supporting importing complex object information from simulators like CARLA.
- Extending the domain to incorporate additional metadata, such as highway entrances and exits.
- Fixing various bugs and limitations that exist in the driving domain (e.g. [Issue #274](https://github.com/BerkeleyLearnVerify/Scenic/issues/274) and [Issue #295](https://github.com/BerkeleyLearnVerify/Scenic/issues/295)).

### Interfacing Scenic to New Simulators

 - **Topics:** `Simulation` `Autonomous Driving`
 - **Skills:** Python
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** {{% mention "dfremont" %}}, {{% mention "evin" %}}

Scenic is designed to be [easily-interfaced to new simulators](https://docs.scenic-lang.org/en/latest/new_simulator.html).
Depending on student interest, we could pick a simulator which would open up new kinds of applications for Scenic and write an interface for it.
Some possibilities include:

- The [AWSIM](https://github.com/tier4/AWSIM) driving simulator (to allow testing the [Autoware](https://autoware.org/) open-source autonomous driving software stack)
- The [CarMaker](https://www.ipg-automotive.com/solutions/product-portfolio/carmaker/) driving simulator

The goal of the project would be to create an interface between Scenic and the new simulator and write scenarios demonstrating it.
If time allows, we could do a case study on a realistic system for publication at an academic conference.

### Tool to Visualize Scenario Distributions

 - **Topics:** `Visualization`
 - **Skills:** Python; basic visualization and graphics
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** {{% mention "dfremont" %}}, {{% mention "evin" %}}

A Scenic scenario represents a distribution over scenes, but it can be difficult to interpret what exactly this distribution represents. Being able to visualize this distribution would be helpful for understanding and reasoning about Scenarios.

The goal of this project would be to build on an existing prototype for visualizing these distributions, and to create a tool that can be used by the wider Scenic community.
