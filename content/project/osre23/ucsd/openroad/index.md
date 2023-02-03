---
title: OpenROAD - An Open-Source, Autonomous RTL-GDSII Flow for VLSI Designs
authors: ["Indira Iyer Almeida", "Matt Liberty"]
author_notes: 
- "Precision Innovations Inc - Consultant at OpenROAD"
- "V.P. Engineering, Precision Innovations- Technical head OpenROAD"
tags: ["osre23", "ucsd", "uc", "chip design", "reproducibility"]
date: 2023-02-01
lastmod: 2023-02-01
---

The [OpenROAD](https://theopenroadproject.org) project is a non-profit, DARPA-funded and Google sponsored project committed to creating low-cost and innovative Electronic Design Automation (EDA) tools and flows for IC design. Our mission is to democratize IC design, break down barriers of cost and access and mitigate schedule risk through native and open source innovation and collaboration with ecosystem partners. [OpenROAD](https://github.com/The-OpenROAD-Project) provides an autonomous, no-human-in-the-loop, 24-hour, RTL-GDSII flow for fast ASIC design exploration, QoR estimation and physical implementation for a range of technologies above 12 nm. We welcome a diverse community of designers, researchers, enthusiasts, software engineers and entrepreneurs to use and contribute to OpenROAD and make a far-reaching impact. OpenROAD has been used in > 600 tapeouts across a range of ASIC applications with a rapidly growing and diverse user community.

### Enhance OpenROAD GUI Flow Manager

  * **Topics**: `GUI`, `Visualization`, `User Interfaces`
  * **Skills**:  C++, Qt
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours) 
  * **Mentor**: [Matt Liberty](mailto:mliberty@precisioninno.com), [Ethan Mahintorabi](mailto:ethanmoon@google.com)

Develop custom features for analysis and  visualizations in the [OpenROAD GUI] (https://openroad.readthedocs.io/en/latest/main/src/gui/README.html)  to support native and third party flows. These include [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts), [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane)  and other third-party flows . Create documentation: commands, developer guide notes, tutorials to show GUI usage for supported flows.

### Profile and tune OpenROAD flow for Runtime improvements
 * **Topics**: `OpenROAD-flow-scripts`, `Flow Manager`, `Runtime Optimization`
  * **Skills**: Knowledge about Computational resource optimization, Cloud-based computation, Basic VLSI design and tools knowledge
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours) 
  * **Mentor**: [Matt Liberty](mailto:mliberty@precisioninno.com), [Ethan Mahintorabi](mailto:ethanmoon@google.com)

Test, analyze and develop verifiable and re-producible strategies to improve run times in [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts). These include optimizations of computational resources over the cloud, tuning of algorithmic and design flow parameters. Create test plans using existing or new designs to show runtime improvements.

### Update OpenROAD Documentation and Tutorials

  * **Topics**: `Documentation`, `Tutorials`, `VLSI design basics`
  * **Skills**:  Knowledge of EDA tools, basics of VLSI design flow, tcl, shell scripts, Documentation, Markdown
  * **Difficulty**: Medium
  * **Size**:  Medium or Large (175 or 350 hours)
  * **Mentor**: [Indira Iyer Almeida](mailto:iiyer@precisioninno.com), [Vitor Bandeira](mailto:vbandeira@precisioninno.com)

Review and update missing documentation and tutorials in [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts) for existing and new features. Here is an example Tutorial link: https://openroad-flow-scripts.readthedocs.io/en/latest/tutorials/FlowTutorial.html for reference.

### LEF and Liberty Model Testing

  * **Topics**: `Testing`, `LEF`, 'LIB', `VLSI design basics`
  * **Skills**:  Knowledge of EDA tools, basics of VLSI design, lef and lib model abstracts, tcl, shell scripts, Verilog, Layout
  * **Difficulty**: Medium
  * **Size**: Medium or Large (175 or 350 hours)
  * **Mentor**: [Matt Liberty](mailto:mliberty@precisioninno.com)

Test the accuracy of generated LIB and LEF models for signoff  in [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts) for flat and hierarchical design flows. Build test cases to validate and add to the regression suite.
