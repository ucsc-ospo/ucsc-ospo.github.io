---
title: "OpenROAD - An Open-Source, Autonomous RTL-GDSII Flow for Chip Design"
authors: [mliberty, luarss]
author_notes: ["VP Engineering, Precision Innovations - Technical Head of OpenROAD", "Individual Contributor at Precision Innovations"]
tags: ["osre25", "ucsd", "uc", "chip design", "asicdesign", "llm", "ml", "ai"]
date: 2025-01-19
---

The [OpenROAD](https://theopenroadproject.org) project is a non-profit project, originally funded by DARPA with the aim of creating open-source EDA tools; an Autonomous flow from RTL-GDSII that completes < 24 hrs,  to lower cost and boost innovation in IC design. This project is now supported by [Precision Innovations](precisioninno.com).

OpenROAD massively scales and supports EWD (Education and Workforce Development) and supports a broad ecosystem making it a vital tool that supports a rapidly growing Semiconductor Industry. 

OpenROAD is the fastest onramp to gain knowledge, skills and create pathways for great career opportunities in chip design. You will develop important software and hardware design skills by contributing to these interesting projects. You will also have the opportunity to work with mentors from the OpenROAD project and other industry experts.

We welcome a diverse community of designers, researchers, enthusiasts, software engineers and entrepreneurs to use and contribute to OpenROAD and make a far-reaching impact in the rapidly growing, global Semiconductor Industry.

### Improving Code Quality in OpenROAD

  * **Topics**: `Coding Best Practices in C++`, `Code Quality Tooling`, `Continuous Integration`
  * **Skills**: C++
  * **Difficulty**: Medium
  * **Size**: Medium (175 hours)
  * **Mentors**: Matt Liberty & Arthur Koucher

OpenROAD is a large and complex program.  This project is to improve the code quality through resolving issues flagged by tools like Coverity and clang-tidy.  New tools like the clang sanitizers ASAN/TSAN/UBSAN should also be set up and integrated with the Jenkins CI.

### GUI Testing in OpenROAD

  * **Topics**: `Testing`, `Continuous Integration`
  * **Skills**: C++, Qt
  * **Difficulty**: Medium
  * **Size**: Large (350 hours)
  * **Mentors**: Matt Liberty & Peter Gadfort

The OpenROAD GUI is a crucial set of functionality for users to see and investigate their design.  GUI testing is specialized and rather different from standard unit testing.  The GUI therefore needs improvements to its testing to cover both interaction and rendering.  The GUI uses the Qt framework.  An open-source testing tool like https://github.com/faaxm/spix will be set up and key tests developed.  This will provide the framework for all future testing.

### Rectilinear Floorplans in OpenROAD

  * **Topics**: `Electronic Design Automation`, `Algorithms`
  * **Skills**: C++, data structures and algorithms
  * **Difficulty**: Medium
  * **Size**: Large (350 hours)
  * **Mentors**: Eder Matheus Rodrigues Monteiro & Augusto Berndt

OpenROAD supports block floorplans that are rectangular in shape.  Some designs may require more complex shapes to fit.  This project extends the tool to support rectilinear polygon shapes as floorplans.  This will require upgrading data structures and algorithms in various parts of OpenROAD including floor plan generation, pin placement, and global placement.

### LEF Reader and Database Enhancements in OpenROAD

  * **Topics**: `Electronic Design Automation`, `Database`, `Parsing`
  * **Skills**: Boost Spirit parsers, Database, C++
  * **Difficulty**: Medium
  * **Size**: Medium (175 hours)
  * **Mentors**: Osama Hammad Abdel Reheem & Ethan Mahintorabi

LEF (Library Exchange Format) is a standard format for describing physical design rules for integrated circuits.   OpenROAD has support for many constructs but some newer ones for advanced process nodes are not supported.  This project is to support parsing such information and storing in the OpenDB for use by the rest of the tool.

### ORAssistant - LLM Data Engineering and Testing

  * **Topics**: `Large Language Model`, `Machine Learning`, `Data Engineering`, `Model Deployment`, `Testing`, `Full-Stack Development`
  * **Skills**: large language model engineering, database, evaluation, CI/CD, open-source or related software development, full-stack
  * **Difficulty**: Medium
  * **Size**: Medium (175 hours)
  * **Mentor**: Jack Luar

This project is aimed at enhancing robustness and accuracy for [OR Assistant](https://woset-workshop.github.io/PDFs/2024/11_ORAssistant_A_Custom_RAG_ba.pdf), the [conversational assistant for OpenROAD](https://github.com/The-OpenROAD-Project/ORAssistant) through comprehensive testing and evaluation. You will work with members of the OpenROAD team and other researchers to enhance the existing dataset to cover a wide range of use cases to deliver accurate responses more efficiently. This project will focus on data engineering and benchmarking and you will collaborate on a project on the LLM model engineering. Tasks include: creating evaluation pipelines, building databases to gather feedback, improving CI/CD, writing documentation, and improving the backend and frontend services as needed (non-exhaustive). You will gain valuable experience and skills in understanding chip design flows and applications. Open to proposals from all levels of ML practitioners.

### ORAssistant - LLM Model Engineering

  * **Topics**: `Large Language Model`, `Machine Learning`, `Model Architecture`, `Model Deployment`
  * **Skills**: large language model engineering, prompt engineering, fine-tuning
  * **Difficulty**: Medium
  * **Size**: Medium (175 hours)
  * **Mentor**: Jack Luar

This project is aimed at enhancing robustness and accuracy for [OR Assistant](https://woset-workshop.github.io/PDFs/2024/11_ORAssistant_A_Custom_RAG_ba.pdf), the [conversational assistant for OpenROAD](https://github.com/The-OpenROAD-Project/ORAssistant) through enhanced model architectures. You will work with members of the OpenROAD team and other researchers to explore alternate architectures beyond the existing RAG-based implementation. This project will focus on improving reliability and accuracy of the existing model architecture. You will collaborate on a tandem project on data engineering for OR assistant. Tasks include: reviewing and understanding the state-of-the-art in retrieval augmented generation, implementing best practices, caching prompts, improving relevance and accuracy metrics, writing documentation and improving the backend and frontend services as needed (non-exhaustive).  You will gain valuable experience and skills in understanding chip design flows and applications. Open to proposals from all levels of ML practitioners.
