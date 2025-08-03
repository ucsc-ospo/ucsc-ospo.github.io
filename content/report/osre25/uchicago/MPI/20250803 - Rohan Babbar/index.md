---
title: "Mid-Term Update: MPI Appliance for HPC Research on Chameleon"
subtitle: ""
summary:
authors: 
  - rohanbabbar04
tags: ["osre25", "reproducibility", "MPI", "cloud computing"]
categories: ["osre25", "reproducibility", "HPC", "MPI"]
date: 2025-08-03
lastmod: 2025-08-03
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

Hi everyone! This is my mid-term blog update for the project [MPI Appliance for HPC Research on Chameleon](https://ucsc-ospo.github.io/project/osre25/uchicago/mpi/), developed in collaboration with Argonne National Laboratory and the Chameleon Cloud community. 
This blog follows up on my earlier post, which you can find [here](https://ucsc-ospo.github.io/report/osre25/uchicago/mpi/20250614-rohan-babbar/).

### 🔧 June 15 – June 29, 2025

Worked on creating and configuring images on Chameleon Cloud for the following three sites: 
CHI@UC, CHI@TACC, and KVM@TACC.

Key features of the images:
- **Spack**: Pre-installed and configured for easy package management of HPC software.
- **Lua Modules (LMod)**: Installed and configured for environment module management.
- **MPI Support**: Both MPICH and Open MPI are pre-installed, enabling users to run distributed applications out-of-the-box.

These images are now publicly available and can be seen directly on the Chameleon Appliance Catalog, titled [MPI and Spack for HPC (Ubuntu 22.04)](https://chameleoncloud.org/appliances/127/).

I also worked on some example Jupyter notebooks on how to get started using these images.

### 🔧 June 30 – July 13, 2025

With the MPI Appliance now published on Chameleon Cloud, the next step was to automate the setup of an MPI-Spack cluster.

To achieve this, I developed a set of Ansible playbooks that:

1) Configure both master and worker nodes with site-specific settings
2) Set up seamless access to Chameleon NFS shares
3) Allow users to easily install Spack packages, compilers, and dependencies across all nodes

These playbooks aim to simplify the deployment of reproducible HPC environments and reduce the time required to get a working cluster up and running.

### 🔧 July 14 – July 28, 2025

This week began with me fixing some issues in python-chi, the official Python client for the Chameleon testbed.
We also discussed adding support for CUDA-based packages, which would make it easier to work with NVIDIA GPUs.
We successfully published a new image on Chameleon, titled [MPI and Spack for HPC (Ubuntu 22.04 - CUDA)](https://chameleoncloud.org/appliances/130/), and added an example to demonstrate its usage.

We compiled the artifact containing the Jupyter notebooks and Ansible playbooks and published it on Chameleon Trovi. 
Feel free to check it out [here](https://chameleoncloud.org/experiment/share/7424a8dc-0688-4383-9d67-1e40ff37de17). The documentation still needs some work.

📌 That’s it for now! I’m currently working on the documentation, a ROCm-based image for AMD GPUs, and some container-based examples. 
Stay tuned for more updates in the next blog.
