---
title: "Final Blog:Improving Usability and Performance in cc-snapshot"
summary:
authors: ["Zahra Temori"]
tags: ["osre25", "reproducibility", "cc-snapshot"]
categories: ["SummerofReproducibility25"]
date: 2025-08-24
lastmod: 2025-08-24
featured: true
draft: false

image:
  caption: ""
  focal_point: Center
  preview_only: false
---

My name is Zahra Temori, and I'm thrilled to collaborate with mentor Paul Marshall during this summer on the cc-snapshot project.

## Introduction
Reproducibility is an important concept in high performance computing and research. It ensures that experiments can be repeated, validated, and extended with confidence. Achieving a reproducible environment requires identical software stacks, with the exact same dependencies, and configuration. The Chameleon Cloud testbed provides the cc-snapshot tool to support reproducibility by capturing the complete state of a running system. This allows researchers to rerun experiments exactly as before, share setups among each other, and avoid potential environmental issues such as missing dependencies or version mismatches. In this work, we explore how to enhance snapshotting as a reproducible method and make it an effective strategy for HPC research.

## Key Achievements
The project was divided into two phases.The first phase focused on usability, reorganizing the tool, and expanding its capabilities. The second phase was benchmarking to evaluate alternative image formats and compression methods to improve snapshotting performance.

1. **Usability Enhancements:**
The original snapshotting tool had challenges including a limited command line, tightly coupled logic, and minimal testing support, which made it difficult for users to interact with and developers to maintain. To enhance the command line interface, we added a flag to disable automatic updates, giving users more control over when to pull the latest version. We also added a dry-run flag to simulate actions before running a snapshot, allowing developers to test and run safely. Moreover, we implemented support for a custom source path, enabling snapshots of specific directories. This helps developers test smaller directories rather than full snapshots, which can be more complicated when testing functionalities.
To improve maintainability, we refactored the codebase into five modular functions, allowing developers to make future changes more easily. In addition, we added automated tests with GitHub Actions to validate new and existing features and ensure that changes work as expected.

2. **Performance Optimization:**
The default format and compression on snapshotting was Qcow2 with zlib, which often resulted in long snapshot creation time. To address this performance issue, we benchmarked other alternatives such as QCOW2 with zstd compression, and RAW with no compression. We also chose three images of varying sizes: small 4.47 GiB, medium 7.62 GiB, and large 12.7 GiB. The medium size image was user created to demonstrate the snapshotting and compression works for both Chameleon-supported images and user-created images.

**Results:**
We ran each image with different compression methods and recorded four key metrics: creation time, upload time, boot time, and final image size. We calculated the overall time of each compression method from experiments on three different image sizes to evaluate which performed better. The results revealed that zstd compression reduced the creation time around 80.6\% across the three image sizes. The upload time for zstd was nearly equal to the zlib method, while RAW images, due to no compression and larger size, uploaded much slower compared to images compressed with zlib and zstd. The boot time was nearly the same across all images, confirming that zlib and zstd take about the same time to uncompress, while RAW images take longer to boot due to large size. Our work suggested that QCOW2 with zstd compression should be used instead of QCOW2 with zlib compression when creating a snapshot. This enables researchers to generate and share reproducible environments faster. 
## Conclusion and Future Work

Snapshotting is a practical way to support reproducibility in HPC, but to be effective, it should be easy to use and fast enough for real research workflows. Our results show that using zstd compression can drop the snapshot creation time by over 80\% compared to the common default zlib compression, without affecting upload or boot performance. Looking ahead, we plan to integrate zstd , try it on more workloads and image types, and explore ways to improve snapshotting for even greater speedups and reliable results.
## Deliverables

- **Repository:** All comprehensive analysis code and source code can be found in the [CC-SNAPSHOT GitHub Repository](https://github.com/ChameleonCloud/cc-snapshot/tree/reproducibility-improvements).
