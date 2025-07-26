---
title: "Halfway Blog - WildBerryEye: Mechanical Design & Weather-Resistant Enclosure"
subtitle: ""
summary: ""
authors: [teolangan]
tags: ["osre25","wildberryeye"]
categories: ["osre25","SoR"]
date:  2025-07-25
lastmod: 2025-07-25
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

Hi everyone! My name is [Teodor Langan](/content/authors/teolangan), and I am an undergraduate studying Robotics Engineering at the University of California, Santa Cruz. I’m happy to share the progress I have been able to make over the last six weeks on my GSoC 2025 project. Over the last six weeks, I have been working on developing the hardware for the [WildBerryEye](/project/osre25/ucsc/wildberryeye/) project, mentored by [Carlos Isaac Espinosa](/content/authors/caiespin).


## Project Overview

The WildBerryEye project enables AI-powered ecological monitoring using Raspberry Pi cameras and computer vision models. However, achieving this requires a reliable enclosure that can support long-term deployment in the wild. The goal for my project is to address this need by designing a modular, 3D-printable camera casing that protects WildBerryEye’s electronics from outside factors such as rain, dust, and bugs, while remaining easy to print and assemble. To achieve this, my main responsibilities for this project include:

* Implementing a modular design and development-friendly features for ease of assembly and flexible use across hardware setups
* Prototyping and testing enclosures outdoors to assess durability, water resistance, and ventilation—then iterating based on results
* Developing clear documentation, assembly instructions, and designing with open-source tools
* Exploring material options and print techniques to improve outdoor lifespan and environmental resilience

Designed largely with FreeCAD and tested in real outdoor conditions, the open-source enclosure will ensure WildBerryEye hardware can be deployed in natural environments for continuous, low-maintenance data collection.


## Progress So Far

Over the past 6 weeks, great progress has been made on the design of the WildBerryEye camera enclosure. Some key accomplishments include:

* **Full 3D Assembly Model of Electronics:** Modeled all core components used in the WildBerryEye system to serve as a reference for enclosure design. For parts without existing CAD models, accurate measurements were taken and custom models were created in FreeCAD.
* **Initial Enclosure Prototype:** Designed and 3D-printed a first full prototype featuring a hinge-latch mechanism to allow tool-free easy access to internal electronics for development and maintenance.
* **Design Iteration Based on Testing:** Based on the results of the first print, created an improved version with better electronics integration, port alignment, and more functionality.


## Challenges & Next Steps

* **Field-Ready Integration:** Preparing for field testing with upcoming prototypes by making sure that all internal electronics are securely mounted and fully accessible within the enclosure.
* **Latch Mechanism Refinement:** Finalizing a reliable hinge-latch design that can keep the enclosure sealed during outdoor use while remaining easy to open for maintenance.
* **Balancing Modularity, Size, and Weatherproofing:** Maintaining a compact form factor without compromising on modularity or weather resistance—especially when routing cables and mounting components.
* **Material Experimentation:** Beginning test prints with TPU, a flexible filament that may provide improved seals or gaskets for added protection.
* **Ventilation Without Exposure:** Exploring airflow solutions such as labyrinth-style vents to enable heat dissipation without letting in moisture or debris.


## Final Thoughts

These past 6 weeks have helped me immensely to grow my skills in mechanical design, CAD modeling, and field-focused prototyping. The WildBerryEye system can help researchers monitor pollinators and other wildlife in their natural habitats without requiring constant in-person observation or high-maintenance setups. By enabling long-term, autonomous data collection in outdoor environments, it opens new possibilities for low-cost, scalable ecological monitoring.

I’m especially grateful to my mentor [Carlos Isaac Espinosa](/content/authors/caiespin) and the WildBerryEye team for their ongoing support. Excited for the second half, where the design will face real-world testing and help bring this impactful system one step closer to field deployment!




