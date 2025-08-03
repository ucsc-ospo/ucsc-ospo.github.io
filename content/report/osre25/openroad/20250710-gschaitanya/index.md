---
title: "Rectilinear Floorplans in OpenROAD"
subtitle: "Implementing support for rectilinear dies in the OpenROAD Floorplanning flow" 
summary:
authors: 
  - gschaitanya 
tags: ["osre25", "gsoc25","openroad",]
categories: ["Electronic Design Automation", "VLSI", "C++", "Algorithms", "Digital Design"]
date: 2025-07-10
lastmod: 2025-07-10
featured: true
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "TopLeft"
  preview_only: false
---

# Google Summer of Code ‘25: Enabling Rectilinear Floorplanning in OpenROAD

This summer, under the guidance of my mentors Eder Monteiro and Augusto Berndt at the OpenROAD project, I am implementing support for **polygonal (specifically rectilinear) die shapes** in OpenROAD’s floorplanning flow.

Here’s a link to my original [proposal](https://summerofcode.withgoogle.com/programs/2025/projects/mcv3Hbgk)

## What is OpenROAD and why polygonal floorplans?

[OpenROAD](https://github.com/The-OpenROAD-Project/OpenROAD) is a fully autonomous RTL-to-GDS digital layout toolchain. The OpenROAD flow delivers an Autonomous, No-Human-In-Loop (NHIL) flow, 24 hour turnaround from RTL-GDSII for rapid design exploration and physical design implementation.

Until now, OpenROAD primarily supported rectangular die shapes in its floorplanning. This limits its use for **advanced packaging, 2.5D/3D ICs, or irregular chiplet-based designs**, where non-rectangular dies are increasingly common.

By extending the floorplanner to handle **rectilinear (non-manhattan, but still axis-aligned) dies**, we open the door for a broader class of cutting-edge VLSI layouts.

---

## Motivation and what gap does this fill?

From my background in electronics engineering, I’ve seen that advanced packaging hsd been unusual die shapes, whether for stacking, interposers, or simply to optimize area and thermal profiles.

Right now, OpenROAD’s inability to handle these non-rectangular dies is a blocker for certain modern flows. My project directly addresses this by:

- Extending the Tcl and internal APIs to accept and validate polygonal die/core shapes.
- Modifying the row generation and site placement algorithms to conform to polygonal boundaries.
- Ensuring that all downstream modules (global placement, detailed placement, routing) can consume the new floorplan data structures without any issues.

## My approach & engineering plan

My work focuses on maintaining **robustness and backward compatibility**, while introducing this major new feature.

- **Floorplan Input**: Users can now specify die/core shapes as sequences of x/y coordinates (`-die_polygon` and `-core_polygon`) directly from the Tcl interface.
- **Data structures**: Extend OpenROAD's internal representations to store arbitrary rectilinear polygons and propagate these safely through the design pipeline.
- **Row Generation**: Develop a new functions (`make_polygon_rows`) to fill polygonal die areas with standard cell rows, properly clipped to the die shape.
- **Verification**: Build rigorous regression and sanity checks. This includes both internal checks and external DEF writeouts that can be visualized in other tools.
- **Testing & Benchmarks**: Prepare a suite of testcases (including complex T-shaped and L-shaped dies) to validate correctness.

I’m especially careful to keep the existing rectangular flow untouched. The new features only engage when the user explicitly specifies polygonal options.

---
## Acknowledgments

I’m deeply grateful to my mentors from the OpenROAD community who have given invaluable guidance - Eder Monteiro and Augusto Berndt. I’m also excited to contribute this to an open-source EDA project that’s shaping the future of accessible hardware design.
![alt text](image.png)
---
