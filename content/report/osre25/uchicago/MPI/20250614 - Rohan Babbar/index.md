---
title: "MPI Appliance for HPC Research on Chameleon"
subtitle: ""
summary:
authors: 
  - rohanbabbar04
tags: ["osre25", "reproducibility", "MPI", "cloud computing"]
categories: ["osre25", "reproducibility", "HPC", "MPI"]
date: 2025-06-14
lastmod: 2025-06-14
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

Hi Everyone,

I’m Rohan Babbar from Delhi, India. This summer, I’m excited to be working with the Argonne National Laboratory and the Chameleon Cloud community. My [project](https://ucsc-ospo.github.io/project/osre25/uchicago/mpi/) focuses on developing an MPI Appliance to support reproducible High-Performance Computing (HPC) research on the Chameleon testbed. 

For more details about the project and the planned work for the summer, you can read my proposal [here](https://docs.google.com/document/d/1iOx95-IcEOSVxpOkL20-jT5SSDOwBiP78ysSUNpRwXs/edit?usp=sharing).

### 👥 Community Bonding Period

Although the project officially started on June 2, 2025, I made good use of the community bonding period beforehand.

- I began by getting access to the Chameleon testbed, familiarizing myself with its features and tools.
- I experimented with different configurations to understand the ecosystem.
- My mentor, {{% mention raffenettik %}}, and I had regular check-ins to align our vision and finalize our milestones, many of which were laid out in my proposal.

### 🔧 June 2 – June 14, 2025

Our first milestone was to build a base image with MPI pre-installed. For this:

- We decided to use [Spack](https://spack.io/), a flexible package manager tailored for HPC environments.
- The image includes multiple MPI implementations, allowing users to choose the one that best suits their needs and switch between them using simple [Lua Module](https://lmod.readthedocs.io/en/latest/) commands.

📌 That’s all for now! Stay tuned for more updates in the next blog.

Thanks for reading!
