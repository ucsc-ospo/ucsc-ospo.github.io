---
title: "OpenRAM"
authors: [jcirimel]
author_notes: ["Ph.D. student, Computer Science & Engineering, UC Santa Cruz"]
tags: [osre23, uc, "chip design"]
date: 2023-02-08
lastmod: 2023-03-15
---

[OpenRAM](https://github.com/VLSIDA/OpenRAM) is an award winning open-source Python framework to create the layout, netlists, timing and power models, placement and routing models, and other views necessary to use SRAMs in ASIC design. OpenRAM supports integration in both commercial and open-source flows with both predictive and fabricable technologies. Most recently, it has created memories that are included on all of the [eFabless/Google/Skywater MPW tape-outs](https://efabless.com/open_shuttle_program/).


### Layout verses Schematic (LVS) visualization

- **Topics:** `VLSI Design Basics`, `Python`
- **Skills:** Python, VLSI, JSON
- **Difficulty:** Easy/Medium
- **Size:** Medium or Large (175 or 350 hours) 
- **Mentors:** {{% mention jcirimel %}}, [Matthew Guthaus](mailto:mrg@ucsc.edu)
- **Contributor(s):** {{% mention Mahnoor-ismail01 %}}

Create a visualization interface to debug layout verses schematic mismatches in [Magic](https://github.com/RTimothyEdwards/magic) layout editor. Results will be parsed from a JSON output of [Netgen](https://github.com/RTimothyEdwards/netgen).

