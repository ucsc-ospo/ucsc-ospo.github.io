---
title: "SLICES/pos: Reproducible Experiment Workflows"
authors: [gallenmu, carle]
author_notes: ["Technical University of Munich"]
tags: [osre24, reproducibility, python, SLICES-RI]
date: 2024-01-06
lastmod: 2024-01-06
---

[SLICES-RI](https://www.slices-ri.eu/) is a european research initiative aiming to create a digital research infrastructure providing an experimental platform for the upcoming decades.
One of the main goals of this initiative is the creation of fully reproducible experiments.
The SLICES research infrastructure will consist of different experiment sites focusing on different research domains such as AI experiments, Cloud and HPC-driven experiments, or investigations on wireless networks.

To achieve reproducibility, the research group on network architectures and services of the Technical University of Munich develops the [SLICES plain orchestrating service (SLICES/pos)](https://dl.acm.org/doi/10.1145/3485983.3494841).
This framework supports a fully automated structured experiment workflow.
The structure of this workflow acts as a template for the design of experiments.
Users that adhere to this template will create inherently reproducible experiments, a feature we call reproducible-by-design.

The SLICES/pos framework currently exists in two versions:
(1) A fully-managed pos deployment, that uses the SLICES/pos framework to manage the entire testbed and (2) a hosted SLICES/pos deployment.
The hosted SLICES/pos deployment is a temporary deployment that runs inside existing testbeds such as [Chameleon](https://chameleoncloud.org/) or [CloudLab](https://cloudlab.us/).

**Additional Information:**

* [plain orchestrating service](https://dl.acm.org/doi/10.1145/3485983.3494841)

### Support Additional Programming Languages

* Topics: `reproducibility`, `statistics`
* Skills: Python
* Difficulty: Medium
* Size: Large (350 hours)
* Mentor: {{% mention gallenmu %}} and {{% mention carle %}}

Design a set of basic examples that demonstrate the usage of pos that can be executed on the SLICES/pos testbed in Munich and the Chameleon testbed.
This set of basic examples acts as a demonstration of pos' capabilities and as a tutorial for new users.
Based on these introductory examples, a more complex experiment shall be designed and executed, demonstrating the portability of the experiments between testbeds.
This experiment involves the entire experiment workflow consisting of the setup and configuration of the testbed infrastructure, the collection of measurement results, and finally, their evaluation and publication.
Multiple results of this experiment shall be created on different testbeds and hardware configurations.
The results of the experiments will differ depending on the different hardware platforms on which the experiment was executed.
These results shall be evaluated and analyzed to find a common connection between the different result sets of the experiments.

* Create introductory examples demonstrating the usage of pos
* Design and create a portable complex network experiment based on SLICES/pos
* Execute the experiment on different testbeds (Chameleon, SLICES/pos testbed)
* Analysis of reproduced experiment
* Automated analysis of experimental results
* Deduction of a model describing the fundamental connections between different experiment executions

