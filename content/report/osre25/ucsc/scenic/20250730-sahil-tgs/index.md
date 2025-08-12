---
title: "Robot Manipulation with Scenic-RoboSuite"
subtitle: "From basic bridge to working pick-and-place"
summary: "Mid-term update on Scenic-RoboSuite integration. Coding phase: Week 7. Status: Bidirectional communication complete, OSC control implemented, visual servoing behaviors working, preparing first prototype release"
authors: 
  - sahil-tgs
tags: ["osre25", "gsoc", "robotics", "probabilistic programming", "scenario specification", "uc", "simulation", "mujoco", "scenic", "manipulation", "control"]
categories: ["GSoC 2025", "Robotics", "Open Source"]
date: 2025-07-30
lastmod: 2025-07-30
featured: true
draft: false

image:
  caption: ""
  focal_point: ""
  preview_only: false
---

We're [Sahil](https://sahiltgs.super.site/), continuing work on the Scenic-RoboSuite integration for GSoC 2025. This [project](https://sahiltgs.super.site/gsoc/uc-ospo-proposal) is mentored by [Daniel Fremont](https://ucsc-ospo.github.io/author/daniel-fremont/) and [Eric Vin](https://ucsc-ospo.github.io/author/eric-vin/).

Since the last update, the [Scenic](https://scenic-lang.org/)-[RoboSuite](https://robosuite.ai/) interface has made significant progress. The bidirectional bridge is now functional - robots can read sensor data and execute behaviors based on observations. However, these features are still in early stages and we're working on making them more stable and consistent.

We've integrated RoboSuite's Operational Space Control into Scenic. This control method lets you command the robot's hand directly in 3D space (like "move 10cm left") instead of calculating complex joint rotations. While the integration works, it's rough around the edges and we're currently focused on stabilizing it across different scenarios.

The main challenge was architectural - RoboSuite expects all robot commands bundled together each timestep, while Scenic processes them one by one. We solved this with a pending actions system that collects everything first, then executes in one go. Time synchronization was another challenge, matching Scenic's steps with MuJoCo's physics.

We've implemented a basic pick-and-place behavior for basic testing. The robot reads sensor data, calculates where to move, and adjusts continuously. It can successfully grasp and lift objects, though consistency varies between runs. The system supports three robot models and works with RoboSuite's pre-built environments.

Custom world building is currently on hold. We've decided to focus on integrating existing RoboSuite features into Scenic first, then build Scenic's capabilities like dynamic scenario randomization on top. For our first prototype, we're aiming to extend the pick-and-place behavior into a full randomization demo - Scenic will randomly position the cube each run, and the robot will adapt to find and grasp it regardless of location.

The next two weeks focus on stabilizing current features and preparing this randomized scenario prototype. Expanding the behavior library and supporting additional environments will come in future phases after we have a solid foundation.

The core bridge between Scenic and RoboSuite is operational, but there's significant work ahead to make it reliable and user-friendly.
