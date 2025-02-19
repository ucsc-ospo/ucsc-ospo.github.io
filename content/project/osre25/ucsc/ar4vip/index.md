---
title: "AR4VIP"
authors: ["alex pang"]
author_notes: ["CSE Professor, UC Santa Cruz"]
tags: ["osre25", "uc", "ar/vr", "navigation aid", "visually impaired people"]
date: 2025-02-18
lastmod: 2025-02-18
---

We are interested in developing navigation aids for visually impaired people (VIP) using AR/VR technologies.
Our intended use is primarily indoors or outdoors but within private confines e.g. person's backyard.
Using AR/VR headsets or smart glasses allows navigation without using a cane and frees
the users' hands for other tasks.

### Continue development on Meta Quest 3 headset

- **Topics:** `Dynamic scenes` `Spatial audio` `Proximity detecction`
- **Skills:** AR/VR familiarity, WebXR, Unity, SLAM, good communicator, good documentation skills
- **Difficulty:** Moderate
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** [alex pang](mailto:pang@soe.ucsc.edu)

Continue development and field testing with the Meta Quest 3 headset.
See this [repository page](https://github.com/sail360/UCSC-VIP-Research) for current status.

Specific tasks:
- Improve spatial audio mapping
- Improve obstacle detection, at different heights, with pre-scanned geometry as well as dynamic objects
  e.g. other people, pets, doors
- Special handling of hazards e.g. stairs, uneven floors, etc.
- Explore/incorporate AI to help identify objects in the scene when requested by user

### New Development on Smart Glasses

- **Topics:** `Continuous Integration` `Continuous Deployment` `DevOps`
- **Skills:** experience with CI/CD, GitHub, Python package deployment
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu), [Anisha Goel](mailto:anishagoel14@gmail.com)

The objective is to setup a CI/CD pipeline that automates the build testing and deployment of the software. The resulting process needs to be robust to contributor errors and work in the distributed conditions of a diverse contributor base.

Specific tasks:
- Automate continuous building, testing, merging and deployment for PolyPhy in GitHub.
- Publish the CI/CD metrics and build assets to the project webpage.
- Work with other contributors in educating them about the best practices of using the developed CI/CD pipeline.
- Add support for automated packaging using common management systems (pip, Anaconda).
