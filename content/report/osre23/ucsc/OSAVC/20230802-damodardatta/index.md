---
title: "Midterm: High Fidelity UAV Simulation Using Unreal Engine with specular reflections"
subtitle: ""
summary: ""
authors: [damodardatta]
author_notes: ["Research Assistant at RRC,IIIT Hyderabad"]
tags: ["osre23"]
categories: ["GSoC'23"]
date: 2023-08-02
lastmod: 2023-08-02
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

As part of the [Open Source Autonomous Vehicle Controller](/project/osre23/ucsc/OSAVC) my [proposal](https://drive.google.com/file/d/18g-WRZj_7ufIt6YZNn4OG1s7VKi1u5hV/view?usp=sharing) under the mentorship of **Aaron Hunter and Carlos Espinosa** aims to Develop a Unreal Engine based simulator for testing. The simulator will be using Unreal Engine for the physics and visualization.

## What we have done so far
- We found that we can use Unreal Engine as a physics simulator and co-simulate with Simulink using the tools provided by MathWorks.
- Simulated a example provided by MathWorks but i wasn't getting the expected behaviour and there were very few resource available.
- So we decided with using Gazebo and ROS for simulation instead of Unreal Engine and Simulink for the example of a balancing bot which had been designed in Solidworks.
- For using Gazebo, i had converted the Solidworks model into an URDF and imported it into Gazebo.

## Future Work
Currently, i am working on using Gazebo and ROS for controling a balancing bot using a PID control algorithm. Afterwards document the process of import a model into Gazebo for testing a control algorithm.
