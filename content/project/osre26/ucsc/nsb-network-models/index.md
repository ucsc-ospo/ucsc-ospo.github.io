---
title: "Network Simulation Bridge • Enabling Interactive Network Models"
authors: [harikrishna-kuttivelil]
author_notes: ["PhD Candidate, CSE, UC Santa Cruz"]
tags: ["osre26", "uc", "networking", "simulation", "iot", "software engineering"]
date: 2026-01-28
lastmod: 2026-01-28
---

The Network Simulation Bridge -- [NSB](https://github.com/nsb-ucsc/nsb) -- is a network co-simulation framework that bridges together applications and network simulators. It enables students, researchers, and developers to prototype their applications and systems on simulated networks. It consists of a message server and client endpoint interfaces which together form a bridge, routing application message payloads through the network simulator. NSB is designed to be extensible through modular interfaces that serve to allow users to contribute new features and modules that suit evolving and emerging use cases. NSB is developed to be application-, network simulator-, and platform-agnostic so that users and developers are empowered to integrate any application front-end with any network simulator back-end, providing versatility and flexibility when used alongside other tools in larger systems and applications.

NSB was created in-house by the [Inter-Networking Research Group](https://inrg.engineering.ucsc.edu/) and is now being developed into a more full-featured open-source tool and ecosystem in partnership with the [UCSC OSPO](https://ucsc-ospo.github.io/) and as part of the [NSF Pathways to Enable Open-Source Ecosystems](https://www.nsf.gov/funding/opportunities/pose-pathways-enable-open-source-ecosystems) program. In this transition to a more polished and feature-rich product, the next phase of NSB development will involve the engineering of new quality-of-life features, testing and iteration of the core tool itself, and user-centric refinement via implementation in interdisciplinary system models.

### Develop a User-Centric Website for NSB

- **Topics:** `Web Development` `Dynamic Updates` `UX`
- **Skills:** web development experience, good communicator, (HTML/CSS), (Javascript)
- **Difficulty:** Moderate
- **Size:** Large
- **Mentors:** [Harikrishna Kuttivelil](mailto:hkuttive@ucsc.edu)

Develop a clean and welcoming landing page and website for the project. The organization needs to reflect the needs of both users and potential project contributors. This website will be the first impression for people new to the project and should 

Specific tasks:
- Work with mentors on understanding the context of the project and the expected needs of the users.
- Port relevant documentation and tutorials from the [repository page](https://github.com/nsb-ucsc/nsb), ensuring updates in the repository are reflected in the website.
- Study existing open source product websites and draw insights to include in our own design.
- Design the structure of the website according to best OS, visual design, and accessibility design practices.
- Include visual content that showcases NSB integration and testimonials (if applicable).

### Improve the User Experience of NSB

- **Topics:** `Software Engineering` `User-Centric Development` `Visualization` `UI/UX` `Documentation`
- **Skills:** package management, toolchain implementation, process automation, technical writing, (visualization), (bash), (Python), (C++)
- **Difficulty:** Moderate
- **Size:** Medium
- **Mentors:** [Harikrishna Kuttivelil](mailto:hkuttive@ucsc.edu)

Our goal has always been to keep NSB streamlined and out of the way of the users and developers. In line with that, we want our tool to be easily available and installable, and we want the experience of using it to feel minimal and non-intrusive while providing sufficient observability of NSB's internals for those who want it.

Specific tasks:
- Work with mentors and potential users on identifying aspects of the user experience that can refined for better quality-of-life experiences.
- Verify and iterate on existing software packaging methods for NSB to ensure that tool setup is stress-free.
- Refine and update existing documentation and tutorials to reflect improvements in the setup, installation, and usage processes.
- Work with mentors and other contributors to work backwards from what the user wants to see to design the user interface.
- Work with other contributors (see below) to develop a *Network-in-a-Box* experience with NSB.

### Create a *Network-in-a-Box* Experience with NSB

- **Topics:** `Software Engineering`, `Simulation`, `System Modeling`, `System Design`, `Visualization`, `UI/UX`
- **Skills:** software integration and interfacing, toolchain implementation, process automation, C++, (visualization), (LLM-enabled code generation), (technical writing)
- **Difficulty:** Challenging
- **Size:** Large
- **Mentors:** [Harikrishna Kuttivelil](mailto:hkuttive@ucsc.edu)

NSB was originally designed for networking graduate students to interface with application-layer programs. But since then, there's been more of an appetite for a simpler *network-in-a-box* approach that would allow users to quickly deploy baseline or generated network simulations that are ready for use with NSB.

Specific tasks:
- Learn how to use one of the major open-source network simulators ([ns3](https://www.nsnam.org/) or [OMNeT++](https://omnetpp.org/)).
- Work with mentors in designing a simpler, minimal user experience of operating NSB.
- Develop tools to automatically create network simulations given input parameters (type of network, number of nodes, description of infrastructure).
- Create documentation aimed at new users.
- Implement or embed network visualizations to enrich the user experience.

### Implement Networked System Models to Evaluate Quality of NSB

- **Topics:** `System Modeling` `Simulation` `System Design` `Software Development` `Product Testing`
- **Skills:** software integration, good communication, qualitative research, (proficiency in Python and/or C++), (processing scientific and technical literature)
- **Difficulty:** Challenging
- **Size:** Large
- **Mentors:** [Harikrishna Kuttivelil](mailto:hkuttive@ucsc.edu)

NSB is a relatively new tool and has not been extensively tested outside of the core contributors, who know a bit too much about the tool. We need to better understand what external user and contributor experience will be like, and the best way to do that is to start developing with NSB to build models of connected systems, i.e., sensor networks, smart homes, smart farms, etc.

Specific tasks:
- Research academic literature and relevant works to identify relevant distributed applications to model.
- Work with mentors and collaborators to plan implementation of selected system models.
- Track and report issues and concerns in quality-of-life experiences, critical errors, or difficulties.
- Work with mentors and contributors to address issues and concerns.
- Refine and update existing documentation and tutorials to reflect improvements in the setup, installation, and usage processes.
- Work with other contributors (see below) in reviewing and cross-referencing model implementations.

### Model Autonomous Vehicle Networks to Drive New Feature Development in NSB

- **Topics:** `System Modeling` `Simulation` `System Design` `Software Development`
- **Skills:** requirement-based software design, message parsing interfaces, server-client communication, (proficiency in Python and/or C++), (processing scientific and technical literature)
- **Difficulty:** Challenging
- **Size:** Large
- **Mentors:** [Harikrishna Kuttivelil](mailto:hkuttive@ucsc.edu)

NSB today serves its named purpose -- message relaying. However, modeling complex systems can sometimes involving synchronizing other simulation features, like *mobility* when dealing with vehivle networks. Implementing a generic layer of being able to synchronize user-defined features across endpoints would be a powerful, enabling feature in NSB. In the process, we may also uncover opportunities for improving the NSB developer experience.

Specific tasks:
- Research academic literature and relevant works to identify and design potential autonomous vehicle network models.
- Work with mentors and collaborators to iterate on system designs to ensure it serves the purpose of furthering NSB development.
- Help mentors design and develop the *new* feature synchronization feature in NSB, driven by the autonomous vehicle system model.
- Develop and iterate feature synchronization, using mobility as the synchronized feature.
- Create documentation and tutorials to serve as resources for future users, contributors, and developers.
- Work with other contributors (see above) in reviewing and cross-referencing model implementations.
