---
title: "MPI Appliance for HPC Research on Chameleon" 
authors: [mpowers]
author_notes: ["University of Chicago", "Argonne National Laboratory"]
tags: ["osre25", "reproducibility", "MPI", "cloud computing"]
date: 2025-02-18
lastmod: 2025-02-18
---

## Overview

This project aims to develop a streamlined template for launching MPI (Message Passing Interface) clusters on the [Chameleon Cloud](chameleoncloud.org) testbed. By configuring disk images with the necessary MPI dependencies and providing orchestration templates that set up networking and instances automatically, researchers will be able to quickly and consistently deploy distributed computing environments. The goal is to facilitate reproducible and scalable computational experiments for a wide range of scientific and engineering applications.

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
**Mentor**: {{% mention msherman %}}, {{% mention mpowers %}}, Ken Raffenetti (raffenet@anl.gov)
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
