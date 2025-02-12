---
title: "Scenic: A Language for Design and Verification of Autonomous Cyber-Physical Systems"
authors: [dfremont]
author_notes: ["Assistant Professor, Computer Science and Engineering, UC Santa Cruz"]
tags: ["osre25", "uc", "ai", "ml", "formal methods", "probabilistic programming"]
date: 2025-02-11
lastmod: 2025-02-11
---

[Scenic](https://scenic-lang.org/) is a probabilistic programming language for the design and verification of autonomous cyber-physical systems like self-driving cars.
Scenic allows users to define *scenarios* for testing or training their system by putting a probability distribution on the system's environment: the positions, orientations, and other properties of objects and agents, as well as their behaviors over time.
Sampling these scenarios and running them in a simulator yields synthetic data which can be used to train or test a system.
Since Scenic was released open-source in 2019, our group and many others in academia have used Scenic to find, diagnose, and fix bugs in autonomous cars, aircraft, robots, and other kinds of systems.
In industry, it is being used by companies including Boeing, Meta, Deutsche Bahn, and Toyota in domains spanning autonomous driving, aviation, household robotics, railways, maritime, and virtual reality.

Our long-term goal is for Scenic to become a widely-used common representation and toolkit supporting the entire design lifecycle of AI-based cyber-physical systems.
Towards this end, we have many summer projects available, ranging from adding new application domains to working on the Scenic compiler and sampler:

1. 3D Driving Scenarios
2. A Library for Aviation Scenarios
3. Interfacing Scenic to new simulators
4. Optimizing and parallelizing Scenic
5. Improvements and infrastructure for the VerifAI toolkit

See the sections below for details.

### 3D Driving Scenarios

 - **Topics:** `Autonomous Driving` `3D modeling`
 - **Skills:** Python; basic vector geometry
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** {{% mention "dfremont" %}}, {{% mention "evin" %}}

Scenic scenarios written to test autonomous vehicles use the [driving domain](https://docs.scenic-lang.org/en/latest/modules/scenic.domains.driving.html), a Scenic library defining driving-specific concepts including cars, pedestrians, roads, lanes, and intersections.
The library extracts information about road networks, such as the shapes of lanes, from files in the standard [OpenDRIVE](https://www.asam.net/standards/detail/opendrive/) format.
Currently, we only generate 2D polygons for lanes, throwing away 3D information.
While this suffices for many driving scenarios, it means we cannot properly model overpasses (the roads appear to overlap) or test driving scenarios where 3D geometry is important, such as hilly terrain.

The goals of this project are to extend our road network library to generate 3D meshes (instead of 2D polygons) for roads, write new Scenic scenarios which use this new capability, and (if time allows) test autonomous driving software using them.

### A Library for Aviation Scenarios

 - **Topics:** `Autonomous Aircraft`
 - **Skills:** Python; ideally some aviation experience
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** {{% mention "dfremont" %}}, {{% mention "evin" %}}

We have used Scenic to find, diagnose, and fix bugs in software for autonomous aircraft: in particular, [this paper](https://arxiv.org/abs/2005.07173) studied a neural network-based automated taxiing system using the [X-Plane](https://www.x-plane.com/) flight simulator.
We also have prototype interfaces to [AirSim](https://microsoft.github.io/AirSim/) and [Microsoft Flight Simulator](https://www.flightsimulator.com/).
However, our experiments so far have mainly focused on simple scenarios involving a single aircraft.

The goal of this project is to develop an *aviation library* for Scenic (like the driving domain mentioned in the previous project) which will allow users to create complex aviation scenarios in a simulator-agnostic way.
The library would define concepts for aircraft, flight paths, weather, etc. and allow importing real-world data about these.
The student would demonstrate the library's functionality by writing some example scenarios and testing either simple aircraft controllers or (if time allows) ML-based flight software.

### Interfacing Scenic to New Simulators

 - **Topics:** `Simulation` `Autonomous Driving` `Robotics` `LLMs`
 - **Skills:** Python
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** {{% mention "dfremont" %}}, {{% mention "evin" %}}

Scenic is designed to be [easily-interfaced to new simulators](https://docs.scenic-lang.org/en/latest/new_simulator.html).
Depending on student interest, we could pick a simulator which would open up new kinds of applications for Scenic and write an interface for it.
Some possibilities include:

- The [AWSIM](https://github.com/tier4/AWSIM) driving simulator (to allow testing the [Autoware](https://autoware.org/) open-source autonomous driving software stack)
- The [CoppeliaSim](https://www.coppeliarobotics.com/) robotics simulator
- NVIDIA's [Cosmos](https://github.com/NVIDIA/Cosmos), an LLM which generates videos from text prompts
- NVIDIA's [Omniverse](https://www.nvidia.com/en-us/omniverse/) (various applications, e.g. simulating virtual factories)
- Various simulators for which we have prototype interfaces that could be generalized and made more usable, including [MuJoCo](https://mujoco.org/) and [Isaac Sim](https://developer.nvidia.com/isaac/sim)

The goal of the project would be to create an interface between Scenic and the new simulator and write scenarios demonstrating it.
If time allows, we could do a case study on a realistic system for publication at an academic conference.

### Optimizing and Parallelizing Scenic

 - **Topics:** `Optimization` `Parallelization`
 - **Skills:** Python
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** {{% mention "dfremont" %}}, {{% mention "evin" %}}

Large-scale testing with Scenic, when one wants to generate thousands of simulations, can be very computationally-expensive.
In some cases, the bottleneck is the simulator, and being able to easily run multiple simulations in parallel would greatly increase scalability.
In others, Scenic itself spends substantial time trying to sample scenarios satisfying all the given constraints.

This project would explore a variety of approaches to speeding up scene and simulation generation in Scenic.
Some possibilities include:

- Parallelizing scene generation and simulation (e.g. using [Ray](https://github.com/ray-project/ray))
- Systematically profiling real-world Scenic programs to characterize the main bottlenecks and propose optimizations
- JIT compiling Scenic's internal sampling code (e.g. using [Numba](https://numba.pydata.org/))

### Improvements and Infrastructure for the VerifAI Toolkit

 - **Topics:** `DevOps` `Documentation` `APIs`
 - **Skills:** Python
 - **Difficulty:** Easy
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** {{% mention "dfremont" %}}, {{% mention "evin" %}}

[VerifAI](https://github.com/BerkeleyLearnVerify/VerifAI) is a toolkit for design and analysis of AI-based systems that builds on top of Scenic.
It adds among other features the ability to perform *falsification*, intelligently searching for scenarios that will cause a system to behave in an undesirable way.

The goal of this project is to improve VerifAI's development infrastructure, documentation, and ease of use, which are currently relatively poor compared to Scenic.
Specific tasks could include:

- Setting up continuous integration (CI) on GitHub
- Creating processes to help users/developers submit issues and PRs and deal with them in a timely manner
- Writing more documentation, including tutorials and examples (not only for end users of VerifAI but those wanting to develop custom falsification components, for example)
- Refactoring VerifAI's API to make it easier to use and extend
