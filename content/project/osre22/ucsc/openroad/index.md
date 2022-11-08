---
title: "OpenROAD - A Complete, Autonomous RTL-GDSII Flow for VLSI Designs"
authors: ["Matthew Guthaus"]
author_notes: ["Professor of Computer Science & Engineering, UC Santa Cruz"]
categories: ["osre22"]
tags: ["uc"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[OpenROAD](https://theopenroadproject.org) is a front-runner in open-source semiconductor design automation tools and know-how. OpenROAD reduces barriers of access and tool costs to democratize system and product innovation in silicon. The OpenROAD tool and flow provide an autonomous, no-human-in-the-loop, 24-hour RTL-GDSII capability to support low-overhead design exploration and implementation through tapeout. We welcome a diverse community of designers, researchers, enthusiasts and entrepreneurs who use and contribute to OpenROAD to make a far-reaching impact. 
Our mission is to democratize and advance design automation of semiconductor devices through leadership, innovation, and collaboration.

OpenROAD is the key enabler of successful Chip initiatives like the Google-sponsored [Efabless](efabless.com) that has made possible more than 150 successful tapeouts by a diverse and global user community. The OpenROAD project repository is https://github.com/The-OpenROAD-Project/OpenROAD.

Design of  static RAMs in VLSI designs for good performance and area is generally time-consuming. Memory compilers significantly reduce design time for complex analog and mixed-signal designs by allowing designers to explore, verify and configure multiple variants and hence select a design that is optimal for area and performance. This project requires the support of memory compilers to [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts) based on popular PDKS such as those provided by [OpenRAM](https://github.com/vlsida/openram). 

### OpenLane Memory Design Macro Floorplanning

  * **Topics**: `Memory Compilers`, `OpenRAM`, `Programmable RAM`
  * **Skills**: python, basic knowledge of memory design, VLSI technology, PDK, Verilog
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours) 
  * **Mentor**: [Matthew Guthaus](mailto:mrg@ucsc.edu), [Mehdi Saligane](mailto:mehdi@umich.edu)

Improve and verify [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane) design planning with OpenRAM memories. Specifically, this project will utilize the macro placer/floorplanner and resolve any issues for memory placement. Issues that will need to be addressed may include power supply connectivity, ability to rotate memory macros, and solving pin-access issues.

### OpenLane Memory Design Timing Analysis

  * **Topics**: `Memory Compilers`, `OpenRAM`, `Programmable RAM`
  * **Skills**: python, basic knowledge of memory design, VLSI technology, PDK, Verilog
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours) 
  * **Mentor**: [Matthew Guthaus](mailto:mrg@ucsc.edu), [Mehdi Saligane](mailto:mehdi@umich.edu)

Improve and verify [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane) Static Timing Analysis using OpenRAM generated library files. Specifically, this will include verifying setup/hold conditions as well as creating additional checks such as minimum period, minimum pulse width, etc. Also, the project will add timing information to Verilog behavioral model.

### OpenLane Memory Macro PDK Support

  * **Topics**: `Memory Compilers`, `OpenRAM`, `Programmable RAM`
  * **Skills**: python, basic knowledge of memory design, VLSI technology, PDK, Verilog
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours) 
  * **Mentor**: [Matthew Guthaus](mailto:mrg@ucsc.edu), [Mehdi Saligane](mailto:mehdi@umich.edu)

Integrate and verify FreePDK45 OpenRAM memories with an [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane) FreePDK45 design flow. OpenLane currently supports only Skywater 130nm PDK, but OpenROAD supports FreePDK45 (which is the same as Nangate45). This project will create a design using OpenRAM memories with the OpenLane flow using FreePDK45.

### VLSI Power Planning and Analysis

  * **Topics**: `Power Planning for VLSI`, `IR Drop Analysis`, `Power grid Creation and Analysis`
  * **Skills**: C++, tcl, VLSI Layout
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours) 
  * **Mentor**: Mehdi Saligane <mailto:mehdi@umich.edu>, Ming-Hung  <mailto:minghung@umich.edu>

Take the existing power planning (pdngen.tcl) module of openroad and recode the functionality in C++ ensuring that all of the unit tests on the existing code pass correctly. Work with a senior member of the team at ARM. Ensure that designs created are of good quality for power routing and overall power consumption.

###  Demos and Tutorials

  * **Topics**: `Demo Development`, `Documentation`, `VLSI design basics`
  * **Skills**:  Knowledge of EDA tools, basics of VLSI design flow, tcl, shell scripts, Documentation, Markdown
  * **Difficulty**: Medium
  * **Size**: Medium (175 hours)
  * **Mentor**: [Indira Iyer Almeida](mailto:dralabeing@openroad.tools), [Vitor Bandeira](mailto:vvbandeira@eng.ucsd.edu)

For [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane), develop demos showing:
The OpenLane flow and highight key features
GUI visualizations
Design Explorations and Experiments
Different design styles and particular challenges

### Comprehensive Flow Testing

  * **Topics**: `Testing`, `Documentation`, `VLSI design basics`
  * **Skills**:  Knowledge of EDA tools, basics of VLSI design, tcl, shell scripts, Verilog, Layout
  * **Difficulty**: Medium
  * **Size**: Medium (175 hours)
  * **Mentor**: [Indira Iyer Almeida](mailto:dralabeing@openroad.tools)

Develop detailed test plans to test the OpenLane flow to expand coverage and advanced features. Add open source designs to the regression test suite to improve tool quality and robustness. This includes design specification, configuration and creation of all necessary files for regression testing. Suggested sources : ICCAS benchmarks, opencores, LSOracle for synthesis flow option.

### Enhance GUI features

  * **Topics**: `GUI`, `Visualization`, `User Interfaces`
  * **Skills**:  C++, Qt
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours) 
  * **Mentor**: [Matt Liberty](mailto:mliberty@eng.ucsd.edu), [Vitor Bandeira](mailto:vvbandeira@eng.ucsd.edu)

For [OpenROAD](https://github.com/The-OpenROAD-Project/OpenROAD), develop and enhance visualizations for EDA data and algorithms in the OpenROAD GUI. Allow deeper understanding of the tool results for users and tool internals for developers.

### Automate OpenDB code Generation

  * **Topics**: `Database`, `EDA`
  * **Skills**:  C++, Python, JSON, Jinja templating
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours)
  * **Mentor**: [Matt Liberty](mailto:mliberty@eng.ucsd.edu), [Tom Spyrou](mailto:aspyrou@eng.ucsd.edu)

For [OpenROAD](https://github.com/The-OpenROAD-Project/OpenROAD)- Automatic code generation for the OpenDB database which allows improvements to the data model with much less hand coding.  Allow the generation of storage, serialization, and callback code from a custom schema description format.
r
### Implement an NLP based AI bot aimed at increasing users, enhancing usability and building a knowledge base

  * **Topics**: `AI`, `ML`, `Analytics`
  * **Skills**:   Python. ML libraries (e.g., Tensorflow, PyTorch)
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours)
  * **Mentor**: [Vitor Bandeira](mailto:vvbandeira@eng.ucsd.edu), [Indira Iyer Almeida](mailto:dralabeing@openroad.tools)

The [OpenROAD](https://github.com/The-OpenROAD-Project/OpenROAD) project contains a storehouse of knowledge in it's Github repositories within Issues and Pull requests. Additionally, project related slack channels also hold useful information in the form of questions and answers, problems and solutions in conversation threads. Implement an AI analytics bot that filters, selects relevant discussions and classifies/records them into useful documentation and actionable issues. This should also directly track, increase project usage and report outcome metrics.
