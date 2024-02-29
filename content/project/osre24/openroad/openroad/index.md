---
title: "OpenROAD - An Open-Source, Autonomous RTL-GDSII Flow for Chip Design"
authors: [iiyer, mliberty, vvbandeira, rovinski, luarss]
author_notes: ["Precision Innovations Inc-Head of Customer Success and Outreach", "V.P Engineering, Precision Innovations- Technical head OpenROAD", "Cloud and DevOps Architect at Precision Innovations & Visiting Scholar UCSD & PhD Candidate UFRGS", "Assistant Professor, New York University", "Student at National University of Singapore"]
tags: ["osre24", "ucsd", "uc", "chip design", "asicdesign"]
date: 2024-01-22
---

The [OpenROAD](https://theopenroadproject.org) project is a non-profit project, originally funded by DARPA with the aim of creating open-source EDA tools; an Autonomous flow from RTL-GDSII that completes < 24 hrs,  to lower cost and boost innovation in IC design. This project is now supported by [Precision Innovations](precisioninno.com).

OpenROAD massively scales and supports EWD (Education and Workforce Development) and supports a broad ecosystem making it a vital tool that supports a rapidly growing Semiconductor Industry. 

OpenROAD is the fastest onramp to gain knowledge, skills and create pathways for great career opportunities in chip design. You will develop important software and hardware design skills by contributing to these interesting projects. You will also have the opportunity to work with mentors from the OpenROAD project and other industry experts.

We welcome a diverse community of designers, researchers, enthusiasts, software engineers and entrepreneurs to use and contribute to OpenROAD and make a far-reaching impact in the rapidly growing, global Semiconductor Industry.

### Create OpenROAD Tutorials and Videos 

  * **Topics**: `Documentation`, `Tutorials`, `Videos`, `VLSI design basics`
  * **Skills**:  Video/audio recording and editing, training and education
  * **Difficulty**: Medium
  * **Size**:  Large (350 hours)
  * **Mentor**: {{% mention iiyer %}}, {{% mention vvbandeira %}}

Create short videos for training and course curriculum highlighting key features and flows in  [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts). 

### Improve the OpenROAD AutoTuner Flow and documentation
 * **Topics**: `OpenROAD-flow-scripts`, `AutoTuner`, `Design Exploration`
  * **Skills**: Knowledge of ML for hyperparameter tuning, Cloud-based computation, Basic VLSI design and tools knowledge, python, C/C++
  * **Difficulty**: Medium
  * **Size**: Large (350 hours) 
  * **Mentor**: {{% mention vvbandeira %}}, {{% mention iiyer %}}

Test, analyze and enhance the [AutoTuner](https://openroad-flow-scripts.readthedocs.io/en/latest/user/InstructionsForAutoTuner.html) to improve usability, documentation and QoR. The Autotuner is an important tool in the OpenROAD flow - [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts) for Chip design exploration that significantly reduces design time.  You will use state-of-the-art ML tools to test the current tool exhaustively for good PPA (performance, power, area) results. You will also update existing documentation to reflect any changes to the tool and flow.

### Implement a memory compiler in the OpenROAD Flow
 * **Topics**: `OpenROAD-flow-scripts`, `Memory Compiler`, 
  * **Skills**: Basic VLSI design and tools knowledge, python, tcl,  C/C++, memory design a plus
  * **Difficulty**: Medium
  * **Size**: Medium (175 hours) 
  * **Mentor**: {{% mention mliberty %}}, {{% mention rovinski %}}

Implement a memory compiler as part of the OpenROAD flow to improve the placement and layout efficiency of large, memory-intensive designs. You will start with an existing code base to develop this feature: https://github.com/The-OpenROAD-Project-staging/OpenROAD/tree/dffram
This is another option: https://github.com/AUCOHL/DFFRAM
Enhance code to support DFFRAM support for the OpenROAD native flow, [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts).

### Integrate a tcl and python linter 

  * **Topics**: `Linting`, `Workflow`
  * **Skills**: tcl,  python, linting
  * **Difficulty**: Easy
  * **Size**: Small  (90 hours) 
  * **Mentor**: {{% mention vvbandeira %}}, {{% mention rovinski %}}

Integrate a tcl and python linter for tools in OpenROAD and [OpenROAD-flow-scripts](https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts) to enforce error checking, style and best practices.


### LLM assistant for OpenROAD - Create Model Architecture and Prototype

  * **Topics**: `Large Language Model`, `Machine Learning`, `Model Architecture`, `Model Deployment`
  * **Skills**:  large language model engineering, prompt engineering, fine-tuning
  * **Difficulty**: Medium
  * **Size**: Medium  (175 hours) 
  * **Mentor**: {{% mention iiyer %}}, {{% mention luarss %}} 

This project involves the creation of a conversational assistant designed around [OpenROAD](https://github.com/The-OpenROAD-Project/OpenROAD) to answer user queries. You will be working in tandem with members of the OpenROAD team and other researchers to deliver a final deployable prototype. You will focus on the design and implementation of modular LLM architectures. You will be experimenting through different architectures and justifying which approach works the best on our domain-specific data. Open to proposals from all levels of ML practitioners.

### LLM assistant for OpenROAD - Data Engineering and testing

  * **Topics**: `Large Language Model`, `Machine Learning`, `Data Engineering`, `Model Deployment`, `Testing`
  * **Skills**:  large language model engineering, prompt engineering, fine-tuning
  * **Difficulty**: Medium
  * **Size**: Medium (175 hours) 
  * **Mentor**: {{% mention iiyer %}}, {{% mention luarss %}} 

This project involves the creation of a conversational assistant designed around [OpenROAD](https://github.com/The-OpenROAD-Project/OpenROAD) to answer user queries. You will be working in tandem with members of the OpenROAD team and other researchers to deliver a final deployable prototype. This project  will focus on the data engineering portion of the project. This may include: training pipelines specifically tailored for fine-tuning LLM models, data annotation, preprocessing and augmentation. Open to proposals from all levels of ML practitioners.

### Create Unit tests for OpenROAD tools
 * **Topics**: `OpenROAD-flow-scripts`, `unit testing`
  * **Skills**: Basic VLSI design and tools knowledge, python, tcl,  C/C++, Github
  * **Difficulty**: Medium
  * **Size**: Medium ( 175 hours) 
  * **Mentor**: {{% mention vvbandeira %}}, {{% mention iiyer %}}

You will build unit tests to test specific features of the OpenROAD tool which will become part of the regression test. Here is an example of a test for UPF support: https://github.com/The-OpenROAD-Project/OpenROAD/blob/master/test/upf/mpd_aes.upf.
This is a great way to learn VLSI flow basics and the art of testing them for practical applications.

