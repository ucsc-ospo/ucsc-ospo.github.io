---
title: "Final Update(Mid-Term -> Final): MPI Appliance for HPC Research on Chameleon"
subtitle: ""
summary:
authors: 
  - rohanbabbar04
tags: ["osre25", "reproducibility", "MPI", "cloud computing"]
categories: ["osre25", "reproducibility", "HPC", "MPI"]
date: 2025-08-31
lastmod: 2025-08-31
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Chameleon Cloud"
  focal_point: Top
  preview_only: false
---

Hi everyone! This is my final update, covering the progress made every two weeks from the midterm to the end of the 
project [MPI Appliance for HPC Research on Chameleon](https://ucsc-ospo.github.io/project/osre25/uchicago/mpi/), developed 
in collaboration with Argonne National Laboratory and the Chameleon Cloud community.
This blog follows up on my earlier post, which you can find [here](https://ucsc-ospo.github.io/report/osre25/uchicago/mpi/20250803-rohan-babbar/).

### 🔧 July 29 – August 11, 2025

With the CUDA- and MPI-Spack–based appliances published, we considered releasing another image variant (ROCm-based) for AMD GPUs.
This will be primarily used in CHI@TACC, which provides AMD GPUs. We have successfully published a new image on Chameleon titled [MPI and Spack for HPC (Ubuntu 22.04 - ROCm)](https://chameleoncloud.org/appliances/131/),
and we also added an example to demonstrate its usage.

### 🔧 August 12 – August 25, 2025

With the examples now available on Trovi for creating an MPI cluster using Ansible and Python-CHI, my next step was to experiment with stack orchestration using Heat Orchestration Templates (HOT) on OpenStack Chameleon Cloud. 
This turned out to be more challenging due to a few restrictions:

1) **OS::Nova::Keypair (new version)**: In the latest OpenStack version, the stack fails to launch if the public_key parameter is not provided for the keypair, as auto-generation is no longer supported.
2) **OS::Heat::SoftwareConfig**: Deployment scripts often fail, hang, or time out, preventing proper configuration of nodes and causing unreliable deployments.

To address these issues, we adopted a new strategy for configuring and creating the MPI cluster: using a temporary bootstrap node.

In simple terms, the workflow of the Heat template is:

1) Provision master and worker nodes via the HOT template on OpenStack.
2) Launch a bootstrap node, install Git and Ansible on it, and then run an Ansible playbook from the bootstrap node to configure the master and worker nodes. This includes setting up SSH, host communication, and the MPI environment.

This provides an alternative method for creating an MPI cluster.

We presented this work on August 26, 2025, to the Chameleon Team and the Argonne MPICH Team. The project was very well received.

Stay tuned for my final report on this work, which I’ll be sharing in my next blog post.
