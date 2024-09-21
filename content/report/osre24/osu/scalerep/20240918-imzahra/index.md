---
title: "[Final] ScaleRep: Reproducing and benchmarking scalability bugs hiding in cloud systems"
summary:
authors: ["imzahra"]
tags: ["osre24", "reproducibility", "scalability"]
categories: ["SummerofReproducibility24"]
date: 2024-09-18
lastmod: 2024-09-18
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

Hello everyone, 

In my SoR 2024 project, [ScaleRep project](/project/osre24/osu/scalerep/) for SoR 2024 under the mentorship of {{% mention bogdanstoica %}} and {{% mention wang.7564 %}}. I’m excited to share the final progress and insights we’ve gathered on tackling scalability bugs in large-scale distributed systems. I aimed to tackle the reproducibility challenges posed by scalability bugs in large-scale distributed systems. Below is a detailed summary of the investigations and findings we've conducted on scalability bugs in large-scale distributed systems.

## Project Overview

As you may recall, our project, ScaleRep, aimed to tackle the challenge of scalability bugs—those insidious issues that often arise in large-scale distributed systems under heavy workloads. These bugs, when triggered, can lead to significant system issues such as downtime, performance bottlenecks, and even data loss. They are particularly difficult to catch using traditional testing methods.

Our primary focus was on reproducing these bugs, documenting the challenges involved, and providing insights into how these bugs manifest under various conditions. This documentation will help researchers identify, benchmark, and resolve similar issues in the future.

## Progress

Since the midterm update, several Apache Ignite bugs have been investigated, some of which have been successfully reproduced and uploaded to Trovi for the research community to access and reuse. Below is the progress on the bugs investigated:

### Bugs Investigated
1. **[IGNITE-20614](https://issues.apache.org/jira/browse/IGNITE-20614)**
2. **[IGNITE-17407](https://issues.apache.org/jira/browse/IGNITE-17407)**
3. **[IGNITE-20602](https://issues.apache.org/jira/browse/IGNITE-20602)**
4. **[IGNITE-16600](https://issues.apache.org/jira/browse/IGNITE-16600)**
5. **[IGNITE-16072](https://issues.apache.org/jira/browse/IGNITE-16072)**
6. **[IGNITE-16582](https://issues.apache.org/jira/browse/IGNITE-16582)**
7. **[IGNITE-16581](https://issues.apache.org/jira/browse/IGNITE-16581)**


## Key Insights & Challenges

1. Complexity of Scalability Bugs
Many scalability bugs involve subtle and complex interactions that are not easily detected in standard testing environments. For instance, IGNITE-20602 only manifested under certain high-load conditions and required a specific workload and environment to reliably trigger the issue. This highlights the importance of large-scale testing when investigating scalability issues.

2. Dependency and Documentation Gaps
We encountered significant challenges with outdated dependencies and incomplete documentation, particularly in older bugs like IGNITE-16072. In these cases, reproducing the bug required extensive modifications or wasn’t feasible without investing disproportionate effort in updating dependencies.

3. Effectiveness of Trovi and Chameleon
Packaging and sharing our reproducible investigations through Trovi and Chameleon have proven highly effective. By providing researchers with pre-configured environments and detailed documentation, we’ve laid the groundwork for future collaboration and further research on these bugs. We expect this to greatly benefit others attempting to reproduce similar issues.

4. Impact of Speed-Based Throttling
Our investigation into IGNITE-16600 revealed several important insights into speed-based throttling and its impact on system performance under high-load conditions. By analyzing the checkpoint starvation and thread throttling mechanisms, we were able to identify areas for improvement in the latest Ignite releases.

## Next Steps
Expanding Collaboration: The packaged bugs and replayable Trovi experiments will be made available to the broader research community, encouraging further investigation and enhancements to large-scale distributed systems.

The ScaleRep project has been an exciting journey into the world of scalability bugs, pushing the boundaries of what’s possible in terms of reproducibility and benchmarking. Through this project, we’ve demonstrated the importance of rigorous testing and comprehensive documentation in improving the reliability of distributed systems.
