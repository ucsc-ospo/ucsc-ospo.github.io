---
# Display name
title: Enhancing h5bench with HDF5 Compression Capability 

# Summary

summary:

# Username (this should match the folder name)
authors:
- henryz
- jeanlucabez

tags: [osre24, uc]
categories: ["GSoC'24"]
date: 2024-05-27
lastmod: 2024-06-14
featured: false
draft: false

image:
  caption: ""
  focal_point: ""
  preview_only: false
---

As part of the [h5bench](/project/osre24/lbl/h5bench) project my [Enhencing h5bench with HDF5 Compression Capability](https://summerofcode.withgoogle.com/myprojects/details/n0H28Z40) under the mentorship of Dr. {{% mention jeanlucabez %}} and Dr. Suren Byna aims to allow users of h5bench to incoporate compression features in their simulations by creating custom benchmarks with common scientific lossless & lossy compression algorithms such as SZ, SZ3, ZFP, and GZIP.  

The problem I am trying to solve is to implement multiple data compression algorithms in h5bench core access patterns through HDF5 filters. This capability should grant users the flexibility to configure the parameters and methods of compression applied to their datasets according to their specific needs and preferences. My solution primarily involves using a user-defined HDF5 filter mechanism to implement lossless and lossy compression algorithms, such as ZFP, SZ, and cuSZ. Throughout the process, I will deliver one C source code implementing compression configuration settings, one C source code implementing lossless and lossy algorithms, a set of performance reports before and after data compression in CSV and standard output files, and a technical documentation on h5bench user manual website.

