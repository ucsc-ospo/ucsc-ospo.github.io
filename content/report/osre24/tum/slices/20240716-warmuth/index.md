---
title: "Halfway Through OSRE24: My Experience and Learnings"
subtitle: "Enhancing Reproducibility and Portability in Open Source Testbeds"
summary: ""
authors: 
  - warmuth
tags: ["osre24", reproducibility]
categories: []
date: 2024-07-15
lastmod: 2024-07-15
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

Hello there! I’m Kilian Warmuth, a computer science student from Germany. This summer, I’m part of the 2024 Summer of Reproducibility (SoR) initiative. My project, "Reproducible Experiment Workflows in SLICES/pos," aims to enhance reproducibility in scientific research, aligning with the FAIR principles (Findable, Accessible, Interoperable, Reusable).

# Project Overview
The "Reproducible Experiment Workflows in SLICES/pos" project is part of the larger SLICES-RI initiative, designed to improve the reproducibility and reusability of large-scale experimental research. The project focuses on integrating the RO-Crate standard into the pos testbed to organize and document experiment results systematically. This integration will enhance the accessibility and comprehensibility of research findings, ensuring they adhere to the FAIR principles. Additionally, the project aims to improve the portability of pos experiments to the Chameleon testbed, facilitating collaboration and seamless execution across different research environments.

# Progress and Challenges
The first half of the project is done, marked by significant progress and learnings. My initial focus was on familiarizing myself with the pos framework and the RO-Crate standard. This foundational knowledge was crucial for the subsequent steps of restructuring the results folder and integrating automated RO-Crate generation into the pos framework.

## Key Achievements:
* Restructured Results Folder: The structure of the results folder has been redesigned to streamline navigation and enable systematic storage of result data.
* Automated RO-Crate Generation: Successfully integrated the basics of the RO-Crate standard into the pos framework, enabling the automated generation of comprehensive results documentation.
* Metadata Documentation: Added comprehensive documentation to the results data, including essential metadata such as author details, user scripts, and hardware information, enhancing reproducibility and interpretability.

## Challenges Encountered:
* Balancing Automation with Flexibility: Ensuring the automated generation of RO-Crates did not compromise the flexibility required by researchers to customize their experiment documentation and mess with the complex requirements of a testbed.
* Complexity of Testbed Systems: FIntegrating the RO-Crate implementation for a complex system like a testbed has required deep dives into the code base of the testbed.

Despite these challenges, the progress made has been rewarding, laying a solid foundation for the next phase of the project.

# Learnings and Skills Gained
**Understanding the Complexity of Testbeds**: One of the key learnings from this project has been the realization that testbeds are complex systems. Despite their complexity, the process became manageable thanks to well-documented software and the invaluable support of top mentors who provided detailed answers to in-depth questions. Their guidance was crucial in navigating the challenges of the project.

**Open Source Development in an Educational Environment**: My experience in open source development has been enriched by working within an educational context. This skill is particularly important when adapting and simplifying code to ensure that users can follow along and gain a deeper understanding of the experiments, improving the quality of research experiments.

# Next Steps
As we move into the second half of this project, our primary focus will be on enhancing the portability of pos experiments to the Chameleon testbed. Key tasks include:

* Finetune RO-Crate Implementation: Continue refining the RO-Crate integration to handle the complexities of testbed systems more effectively like special edge cases.
* Enhance Portability: Refine the integration with Trovi, ensuring seamless upload and retrieval of experiment results across testbeds.
* Develop Introductory Examples: Create examples demonstrating the use of pos in various testbed environments to guide researchers.
* Execute and Analyze Experiments: Design and execute a complex network experiment on both SLICES/pos and Chameleon, validating and refining portability features.

These steps are crucial to achieving our goal of making pos experiments more accessible and reproducible across different research environments.

# Conclusion
Reflecting on the first half of my OSRE24 journey, I am incredibly grateful for the opportunity to work on the "Reproducible Experiment Workflows in SLICES/pos" project. The experience has been both challenging and rewarding, providing valuable insights into open-source development, machine learning techniques, and the creation of educational resources.

As we move forward, I am excited about the coming weeks. The completion of the portability enhancements and the execution of complex experiments lie ahead, marking significant milestones in our project. The skills and lessons I have acquired will guide me in future endeavors.
