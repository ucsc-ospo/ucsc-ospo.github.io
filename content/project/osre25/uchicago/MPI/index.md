---
title: "MPI Appliance for HPC Research on Chameleon"
authors: [raffenettik]
author_notes: ["Argonne National Laboratory"]
tags: ["osre25", "reproducibility", "MPI", "cloud computing"]
date: 2025-02-18
lastmod: 2025-02-18
---

## Overview

Message Passing Interface (MPI) is the dominant programming model for high-performance computing (HPC), enabling applications to scale efficiently across thousands of processing cores. In reproducibility initiatives for HPC research, MPI implementations are critical as they manage the complex communications that underpin parallel scientific applications. However, reproducing MPI-based experiments remains challenging due to the need for specific library versions, network configurations, and multi-node setups that must be precisely orchestrated. 

The popularity of an “MPI cluster” as a base layer for many results in HPC caused support for MPI template and appliance to be specifically requested by the SC24 reproducibility chair to support the conference's reproducibility initiative, providing researchers with standardized environments for validating results. By extending the work begun for SC24, this project aims to create higher-quality, ready-to-use, and maintainable  MPI environments for the Chameleon testbed that abstracts away complex configuration details while ensuring consistent performance across experiments—thus making HPC experiments more accessible and reproducible for the broader research community.

You will lead efforts to configure disk images with the necessary MPI dependencies and provide orchestration templates that set up networking and instances automatically. The resulting appliance will allow researchers to quickly and consistently deploy distributed computing environments with MPI. The goal is to facilitate reproducible and scalable computational experiments for a wide range of scientific and engineering applications.

# Key Outcomes
- Ready-to-Use MPI Disk Images: Create one or more images pre-configured with the correct versions of MPI and dependencies, ensuring a consistent environment.
- Simple Cluster Configuration Scripts: Provide scripts or playbooks that efficiently bring up a fully functional MPI cluster on Chameleon, abstracting away manual setup steps.
- Orchestration Template: An automated workflow that sets up networks, instances, and additional resources needed to run large-scale MPI workloads.

**Topics**: High-Performance Computing (HPC), Cloud Computing, MPI & Distributed Systems, DevOps & Automation

**Skills**:
- MPI & Parallel Programming: Understanding of MPI libraries, cluster configuration, and typical HPC workflows.
- Cloud Orchestration: Familiarity with OpenStack Heat or other Infrastructure-as-Code (IaC) tools for provisioning resources.
- Linux System Administration: Experience configuring and troubleshooting packages, network settings, and performance optimizations.
- Scripting & Automation: Ability to write scripts (e.g., Bash, Python) to automate setup and deployment steps.

**Difficulty**: Moderate to Hard

**Size**: Medium

**Mentor**: {{% mention raffenettik %}}

**Tasks**
- Disk Images with MPI Dependencies
	- Build base images with the correct versions of MPI (e.g., MPICH, OpenMPI) and any required libraries (e.g., GCC, network libraries).
	- Ensure all packages are up to date and tested for compatibility with Chameleon’s bare metal and/or VM environments.
- Cluster Setup Scripts
	- Develop lightweight scripts or Ansible playbooks that join new instances into an MPI cluster, configuring hostnames, SSH keys, and MPI runtime settings.
	- Validate cluster functionality by running simple distributed “Hello World” tests and more advanced benchmarks (e.g., Intel MPI Benchmarks).
- Orchestration Template
	- Provide a Heat template (or similar) specifying the network configuration, instance counts, and environment variables for MPI.
	- Enable easy parameterization of cluster size, disk images, and other variables so users can customize their setups on the fly.
- Integration & Testing
	- Document best practices for launching and using the MPI images in Chameleon.
	- Demonstrate reproducibility with multiple cluster sizes and workloads to ensure reliability.