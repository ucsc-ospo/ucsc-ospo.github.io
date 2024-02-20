---
title: "EdgeRep: Reproducing and benchmarking edge analytic systems" 
authors: [yuyangh, junchenj]
author_notes: [PhD Student at the University of Chicago, Assistant Professor at the University of Chicago]
tags: [osre24, reproducibility, video analytic, machine learning]
date: 2024-02-02
lastmod: 2024-02-06
---

- **Topics:** video analytics, machine learning
- **Skills:** Python, PyTorch, Bash scripting, Linux, Machine Learning modeling 
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** {{% mention yuyangh %}} (contact person), {{% mention junchenj %}}

**Project Idea Description**

With the flourishing of ideas like smart cities and smart manufacturing, a
massive number of edge devices (e.g., traffic or security cameras,
thermometers, flood sensors, etc.) are deployed and connected to the network.
These devices collect and analyze data across space and time, aiding
stakeholders like city governments and manufacturers in optimizing their plans
and operations. However, the sheer number of edge devices and the large amount
of communication among the devices and central servers raises significant
challenges in how to manage and schedule resources. This includes network
bandwidth between the devices and computing power on both edge devices and bare
metal servers, all to maintain the reliable service capability of running
applications.

Moreover, given the limited resources available to edge devices, there's an
emerging trend to reduce average compute and/or bandwidth usage. This is
achieved by leveraging the uneven distribution of interesting events with
respect to both time and space in the input data. This, in turn, introduces
further challenges in provisioning and managing the amount of resources
available to edge devices. The resource demands of running applications can
greatly depend on the input data, which is both dynamic and unpredictable.

Keeping these challenges in mind, the team previously designed and implemented
a dynamic resource manager capable of understanding the applications and making
decisions based on this understanding at runtime. However, such a resource
manager has only been tested with a limited number and types of video analytic
applications. Thus, through the OSRE24 project, we aim to:

- Collect a wide range of videos to form a comprehensive video dataset
- Reproduce other state-of-art self-adaptive video analytic applications
- Package the dataset as well as the application to publish them on Chameleon
  Trovi site

**Project Deliverable**
- Collect a wide range of videos to form a comprehensive video dataset
- Reproduce other state-of-art self-adaptive video analytic applications
- Package the dataset as well as the application to publish them on Chameleon
  Trovi site




