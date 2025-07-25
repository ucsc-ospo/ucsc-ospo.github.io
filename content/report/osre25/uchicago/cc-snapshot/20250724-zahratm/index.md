---
title: "Improving Usability and Performance in cc-snapshot: My Midterm Update"
summary:
authors: ["zahratm"]
tags: ["osre25", "reproducibility", "cc-snapshot"]
categories: ["SummerofReproducibility25"]
date: 2024-07-24
lastmod: 2024-07-24
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "CC-Snapshot performance and usability improvement"
  focal_point: Center
  preview_only: false
---
Hi! I'm Zahra Temori, a rising junior studying Computer Science at the University of Delaware. This summer, I’ve had the exciting opportunity to participate in the Chameleon Summer Reproducibility Program, where I’ve been working under the mentorship of Paul Marshall.
In this blog post, I’d love to share a midterm update on my project [cc-snapshot](https://github.com/ChameleonCloud/cc-snapshot) and highlight what I’ve accomplished so far, what I’ve learned, and what’s coming next. It's been a challenging but rewarding experience diving into real-world research and contributing to tools that help make science more reproducible!

## Project Overview 

CC-Snapshot is a powerful tool on the Chameleon testbed that enables users to package their customized environments for reproducibility and experiment replication. In research, reproducibility is essential. It allows scientists to run experiments consistently, share complete setups with others, and avoid environment-related errors. However, the current snapshotting mechanism has limitations that make it unreliable and inefficient, particularly in terms of usability and performance. These issues can slow down workflows and create barriers for users trying to reproduce results. Our goal is to improve both the usability and performance of the cc-snapshot tool. A more user-friendly and optimized system means that users can create and restore snapshots more quickly and easily, without needing to manually rebuild environments, ultimately saving time and improving reliability in scientific computing.

## Progress So Far

To structure the work, we divided the project into two main phases:
  1. Improving usability, and
  2. Optimizing performance.

I’ve nearly completed the first phase and have just started working on the second.

## Phase One – Usability Improvements

The original version of the cc-snapshot tool had several usability challenges that made it difficult for users to interact with and for developers to maintain. These issues included a rigid interface, lack of flexibility, and limited testing support. All of which made the tool harder to use and extend.
To address these, I worked on the following improvements:

**Problem**: The command-line interface was limited and inflexible. Users couldn’t easily control features or customize behavior, which limited their ability to create snapshots in different scenarios.

**Solution**: I enhanced the CLI by adding:
- A flag to disable automatic updates, giving users more control.
- A --dry-run flag to simulate actions before actually running them which is useful for testing and safety.
- Support for a custom source path, allowing snapshots of specific directories. This makes the tool much more useful for testing smaller environments.
 
**Problem**: The code lacked automated tests. Without tests, developers have to manually verify everything, which is time-consuming and error-prone.

**Solution**: I implemented a basic test suite and integrated it with GitHub Actions, so the tool is automatically tested on every pull request.

**Problem**: The tool didn’t follow a modular design. The logic was tightly coupled, making it hard to isolate or extend parts of the code.

**Solution**: I refactored the code by extracting key functions. This makes the code cleaner, easier to understand, and more maintainable in the long term.

## Next Steps – Phase Two: Performance Optimization

After improving the usability of the cc-snapshot tool, the next phase of the project focuses on addressing key performance bottlenecks. Currently, the snapshotting process can be slow and resource-intensive, which makes it less practical for frequent use especially with large environments.

**Problem 1: Slow Image Compression** 
The current implementation uses the qcow2 image format with zlib compression, which is single-threaded and often inefficient for large disk images. This leads to long snapshot creation times and high CPU usage.

**Solution**: I will benchmark and compare different compression strategies, specifically:
- qcow2 with no compression
- qcow2 with zstd compression, which is faster and multi-threaded
- raw image format, which has no compression but may benefit from simpler processing 

These tests will help determine which method provides the best tradeoff between speed, size, and resource usage.

**Problem 2: Suboptimal Storage Backend** 
Snapshots are currently uploaded to Glance, which can be slow and unreliable. Uploading large images can take several minutes, and this slows down the user workflow.

**Solution**: I will compare Glance with a faster alternative, the Object Store. Smaller, compressed images may upload significantly faster to the Object Store e.g. 30 seconds vs. 2 minutes. By measuring upload speeds and reliability, I can recommend a better default or optional backend for users.

## How I will Measure Performance 

To understand the impact of different strategies, I will try to collect detailed metrics across three stages:
1. Image creation: How long it takes to build the image, depending on compression and format
2. Image upload: How quickly the snapshot can be transferred to Glance or Object Store
3. Instance boot time: How fast a new instance can start from that image (compressed formats must be decompressed)

I will run multiple tests for each scenario and record performance metrics like CPU usage, memory usage, disk throughput, and total time for each step. This will help identify the most efficient and practical configuration for real-world use. 

## Conclusion

Addressing the current usability and performance issues in cc-snapshot is essential to improving the overall user experience. By making the tool easier to use, faster, and more flexible, we can support researchers and developers who depend on reproducible computing for their work. So far, I’ve worked on enhancing the tool’s interface, adding testing support, and refactoring the codebase for better maintainability. In the next phase, I’ll be focusing on benchmarking different compression methods, image formats, and storage backends to improve speed and efficiency.
These improvements will help make cc-snapshot a more powerful and user-friendly tool for the scientific community. 

Stay tuned for the next update and thank you for following my journey!


