---
title: "Reproduce and benchmark self-adaptive edge applications under dynamic resource management"
authors: ["Junchen Jiang"]
author_notes: ["Assistant Professor, University of Chicago"]
tags: ["osre23", "reproducibility", "video analytics", "resource management"]
date: 2023-02-02T00:15:56-07:00
lastmod: 2023-02-02T00:15:56-07:00
---

With the flourishing of the ideas like smart cities or smart manufacturing, a massive amount of edge devices (e.g., traffic or security cameras, thermometers, flood sensors, et al.) are deployed and connected to the network to collect/analyze data across the space and time and help the stakeholders like city governments or manufacturers optimizing their plans and operations. Such a large number of edge devices and large amount of communications among the devicesdd or to the central servers rise a big challenge on how to manage/schedule the resource (i.e., network bandwidth between the devices and/or computing power on both edge devices and bare metal servers) to ensure the running applications' capability of providing a reliable service. Furthermore, with the nature of limited resources available to the edge devices, there is an uprising trend to reduce the average compute and/or bandwidth usage by leveraging the uneven distribution of interesting events with respect to both time and space in the input data. This brings further challenges for provisioning and managing the amount of resources available to the edge devices, as the running applications' resource demands can greatly depend on the input data which is both dynamic and unpredictable.

With these challenges in mind, the team previously designed and implemented a dynamic resource manager that could understand the applications and make decisions based on such understanding at run time. This understanding is achieved based on a key insight - applications will have different magnitudes of performance improvement/degradation toward the change in the amount of resources available depending on the input data and how many resources the applications currently have, which we define as applications' sensitivities. However, such a resource manager has only been tested with a limited number and types of video analytic applications. Hence, through the OSRE23 project, we aim to:

1. reproduce other state-of-art self-adaptive video analytic applications,
2. integrate the reproducible applications into the resource manager framework, 
3. compare the performance with and without resource manager.

### Reproduce/benchmark the self-adaptive video analytic applications' performance under dynamic resource management

- **Topics:** Benchmark, Reproducibility, Video analytics, Machine Learning, Resource Management
- **Skills:** Python, PyTorch, TensorFlowd
- **Difficulty:** Challenging
- **Size:** Large (350 hours)
- **Mentors:** [Junchen Jiang](mailto:junchenj@uchicago.edu), [Yuyang Huang](mailto:yuyangh@uchicago.edu)

Integrate various types of video analytic applications into the aforementioned dynamic resource manager and reproduce/benchmark the applications' performance.

Specific tasks:
- Reproduce state-of-art video analytic applications
- Integrate such applications into the resource manager framework - Benchmark video analytic applications
- Analysis the benchmarked performance results