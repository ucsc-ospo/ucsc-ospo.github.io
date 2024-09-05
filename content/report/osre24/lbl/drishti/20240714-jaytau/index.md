---
title: Midway Through GSoC
subtitle: My Journey with Drishti
summary:
authors: 
- jaytau
- jeanlucabez
author_notes: ["CS Undergrad, BITS Pilani"]
tags: ["osre24", "uc", "LBNL", "data science", "visualization", "performance analysis", "I/O", "HPC", "AI"]
categories: ["GSoC'24"]
date: 2024-07-31
lastmod: 2024-08-06
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hello everyone! I'm {{% mention jaytau %}}, and I'm excited to share my progress update on the [Drishti](https://github.com/hpc-io/drishti) project as part of my Google Summer of Code (GSoC) experience. Over the past few weeks, I've been diving deep into the world of I/O visualization for scientific applications, and I'm thrilled to tell you about the strides we've made.

## What is Drishti?

For those unfamiliar with Drishti, it's an application used to visualize I/O traces of scientific applications. When running complex scientific applications, understanding their I/O behavior can be challenging. Drishti steps in to parse logs from various sources, with a primary focus on those collected using [Darshan](https://wordpress.cels.anl.gov/darshan/), a lightweight I/O characterization tool for HPC applications. Drishti provides human-interpretable insights on how to improve I/O performance based on these logs. While Drishti supports multiple log sources, our current work emphasizes Darshan logs due to their comprehensive I/O information. Additionally, Drishti offers visually appealing and easy-to-understand graphs to help users better grasp their application's I/O patterns, making it easier to identify bottlenecks and optimize performance.

## Progress and Challenges

### Export Directory Feature

One of the first features I implemented was the export directory functionality. In earlier versions of Drishti, users couldn't select where they wanted their output files to be saved. This became problematic when working with read-only log locations. I familiarized myself with the codebase, created a pull request, and successfully added this feature, allowing users to choose their preferred output location.

### CI Improvements and Cross-Project Dependencies

While working on Drishti, I discovered the tight coupling between various tools in the HPC I/O organization, such as Drishti and DXT Explorer. This highlighted the need for improved Continuous Integration (CI) practices. We currently run about eight GitHub Actions for each pull request, but they don't adequately test the interactions between different branches of these interconnected tools. This is an area we've identified for future improvement to ensure smoother integration and fewer conflicts between projects.

### Refactoring for Multi-File Support

The bulk of my time was spent refactoring Drishti to extend its framework from parsing single Darshan files to handling multiple files. This task was more complex than it initially appeared, as Drishti's insights are based on the contents of each Darshan file. When dealing with multiple files, we needed to find a way to aggregate the data meaningfully without sacrificing on performance.

The original codebase had a single, thousand-line function for parsing Darshan files. To improve this, I implemented a data class structure in Python. This refactoring allows for:

1. Better separation of computation and condition checking
2. Easier parallelization of processing multiple traces
3. Finer-grained profiling of performance bottlenecks
4. More flexibility in data manipulation and memory management

## Learnings and Skills Gained

Through this process, I've gained valuable insights into:

1. Refactoring large codebases
2. Understanding and improving cross-project dependencies
3. Implementing data classes in Python for better code organization
4. Balancing performance with code readability and maintainability

## Next Steps

As I move forward with the project, my focus will be on:

1. Adding unit tests for individual methods to ensure functionality
2. Exploring alternative data frame implementations like Polars for better performance
3. Developing aggregation methods for different types of data across multiple Darshan files
4. Optimizing memory usage and computational efficiency for large datasets

## Conclusion

Working on Drishti has been an incredible learning experience. I've had the opportunity to tackle real-world challenges in scientific computing and I/O visualization. As we progress, I'm excited about the potential impact of these improvements on the scientific community's ability to optimize their applications' I/O performance.

I'm grateful for this opportunity and looking forward to the challenges and discoveries that lie ahead in the second half of my GSoC journey. Stay tuned for more updates as we continue to enhance Drishti!

If you have any questions or would like to learn more about the project, feel free to [reach out to me](https://www.jaytau.com/#contact?ref=uc-ospo). Let's keep pushing the boundaries of scientific computing together!
