---
title: "Final Post: Enhancing Reproducibility and Portability in Network Experiments"
subtitle: ""
summary: ""
authors:
  - warmuth
tags: ["osre24", reproducibility]
categories: [SoR]
date: 2024-09-05
lastmod: 2024-09-05
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

## Introduction

As my project with the Summer of Reproducibility (SoR) 2024 comes to a close, I’d like to reflect on the journey and the outcomes achieved. My project focused on **enhancing the reproducibility and portability of network experiments** by integrating the **RO-Crate standard** into the **TUM intern testbed pos (plain orchestrating service)**, and deploying this testbed on the **Chameleon cloud infrastructure**. The aim was to ensure that experiments conducted on one platform could be seamlessly reproduced on another, adhering to the **FAIR principles** (Findable, Accessible, Interoperable, Reusable) for research data.

## Project Recap

The core goal was to make the experiments reproducible and portable between different testbeds like TUM’s pos and Chameleon. To achieve this, I integrated the **RO-Crate standard**, which ensures that all experiment data is automatically documented and stored with metadata, making it easier for others and especially for machines to understand, replicate, and build on the results. Additionally, deploying a lightweight version of pos on the **Chameleon testbed** enabled cross-testbed execution, allowing experiments to be replicated across both environments without significant modifications.

## Key Achievements

Over the course of the project, several key milestones were achieved:

- **RO-Crate Integration**: The first step was restructuring the results folder and automating the generation of metadata using RO-Crate. This ensured that all experiment data was comprehensively documented with details like author information, hardware configurations, and experiment scripts resulting in comprehensive `ro-crate-metadata.json` files as important part of each result folder.

- **Improved Data Management**: The integration of RO-Crate greatly simplified the process of organizing and retrieving experiment data and metadata with information about the experiment and the result files. All metadata was automatically generated, making it easier to share and document the experiments for other researchers to replicate.

- **Automatic Upload to Zenodo**: Another crucial achievement was the implementation of automatic uploading of pos experiment result folders to **Zenodo**, an open-access repository. This step significantly improved the reproducibility and sharing of experiment results, making them easily accessible to the broader scientific community. By utilizing Zenodo, we ensured that experiment results, along with their RO-Crate metadata, could be archived and referenced, fostering greater transparency and collaboration in scientific research.

- **Chameleon Deployment**: Deploying the pos testbed within the Chameleon environment required managing various complexities, particularly related to Chameleon’s OpenStack API, networking setup, and hardware configurations. Coordinating the network components and infrastructure to support pos functionality in this testbed environment demanded significant adjustments to ensure smooth integration and operation.

## Challenges

Like any project, this one came with its own set of challenges:

- **Balancing Automation and Flexibility**: While automating the generation of RO-Crate metadata, it was crucial to ensure that the flexibility required by researchers for customizing their documentation was not compromised. Finding this balance required in-depth adjustments to the testbed infrastructure.

- **Complexity of Testbed Systems**: Integrating RO-Crate into a complex system like pos, and ensuring it works seamlessly with Chameleon, involved understanding and adapting to the complexities of both testbeds.

## Future Directions

As I move forward with my master's thesis working on these challenges, we plan to expand on this work by:

- **Extending the Chameleon Deployment**: We aim to deploy the full version of pos on Chameleon, supporting more complex and larger-scale experiments.

- **Supporting Complex Experiment Workflows**: Future work will focus on handling more intricate and larger datasets, ensuring reproducibility for complex workflows. Only by executing more complex experiments will we be able to thoroughly analyze and compare the differences between executions in pos and the pos deployed on Chameleon, helping us better understand the impact of different testbed environments on experiment outcomes.

- **Automation**: The ultimate goal is to fully automate the process of experiment execution, result documentation, and sharing across testbeds, reducing manual intervention and further enhancing reproducibility.

## Reflections

By integrating the RO-Crate standard and deploying pos on the Chameleon testbed, we have made significant steps toward enhancing the reproducibility, accessibility, and portability of network experiments across research platforms. These efforts contribute to more shareable, and replicable research processes in the scientific community.

I am excited about the future work ahead and am grateful for the mentorship and support I received during this project.

## Deliverables and Availability

Due to the current non-public status of the pos framework, **the code and deliverables are not publicly available** at the moment.

## Previous Blogs

Make sure to check out my other blogs to see how I started this project and the challenges I faced along the way:

- [Introduction](/report/osre24/tum/slices/20240517-warmuth/)
- [Midterm Blog](/report/osre24/tum/slices/20240716-warmuth/)

Servus!
