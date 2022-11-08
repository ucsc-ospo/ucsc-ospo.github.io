---
title: "OpenRAM"
authors: ["Matthew Guthaus"]
author_notes: ["Professor of Computer Science & Engineering, UC Santa Cruz"]
categories: ["osre22"]
tags: ["uc"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[OpenRAM](https://github.com/VLSIDA/OpenRAM) is an award winning open-source Python framework to create the layout, netlists, timing and power models, placement and routing models, and other views necessary to use SRAMs in ASIC design. OpenRAM supports integration in both commercial and open-source flows with both predictive and fabricable technologies. Most recently, it has created memories that are included on all of the [eFabless/Google/Skywater MPW tape-outs](https://efabless.com/open_shuttle_program/).

### Replace logging framework with library

- **Topics:** `User Interfaces`, `Python APIs`
- **Skills:** Python
- **Difficulty:** Easy
- **Size**: Medium (175 hours) 
- **Mentors:** [Matthew Guthaus](mailto:mrg@ucsc.edu),[Jesse Cirimelli-Low](mailto:jcirimel@ucsc.edu)

Replace the custom logging framework in OpenRAM with [Python logging](https://docs.python.org/3/library/logging.html) module. New logging should allow levels of detail as well as tags to enable/disable logging of particular features to aid debugging.

### ROM generator

- **Topics:** `VLSI Design Basics`, `Memories`, `Python`
- **Skills:** Python, VLSI
- **Difficulty:** Medium/Challenging
- **Size**: Large (350 hours) 
- **Mentors:** [Matthew Guthaus](mailto:mrg@ucsc.edu)

Use the OpenRAM API to generate a Read-Only Memory (ROM) file from an input hex file. Project
will automatically generate a Spice netlist, layout, Verilog model and timing characterization.

### Register File generator

- **Topics:** `VLSI Design Basics`, `Memories`, `Python`
- **Skills:** Python, VLSI
- **Difficulty:** Medium/Challenging
- **Size**: Large (350 hours) 
- **Mentors:** [Matthew Guthaus](mailto:mrg@ucsc.edu)

Use the OpenRAM API to generate a Register File from standard library cells. Project
will automatically generate a Spice netlist, layout, Verilog model and timing characterization.

### Built-In Self Test and Repair

- **Topics:** `VLSI Design Basics`, `Python`, `Verilog`, `Testing`
- **Skills:** Python, Verilog
- **Difficulty:** Medium/Challenging
- **Size:** Medium (175 hours)
- **Mentors:** [Matthew Guthaus](mailto:mrg@ucsc.edu), [Bugra Onal](mailto:bonal@ucsc.edu)

Finish integration of parameterized Verilog modeule to support Built-In-Self-Test and Repair
of OpenRAM memories using spare rows and columns in OpenRAM memories. 

### Layout verses Schematic (LVS) visualization

- **Topics:** `VLSI Design Basics`, `Python`
- **Skills:** Python, VLSI, JSON
- **Difficulty:** Easy/Medium
- **Size**: Medium or Large (175 or 350 hours) 
- **Mentors:** [Matthew Guthaus](mailto:mrg@ucsc.edu),[Jesse Cirimelli-Low](mailto:jcirimel@ucsc.edu)

Create a visualization interface to debug layout verses schematic mismatches in [Magic](https://github.com/RTimothyEdwards/magic) layout editor. Results will be parsed from a JSON output of [Netgen](https://github.com/RTimothyEdwards/netgen).

