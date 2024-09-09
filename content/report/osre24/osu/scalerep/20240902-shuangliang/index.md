---
title: "Reflecting on the ScaleRep Project: Achievements and Insights"
subtitle: 
summary: "Reproducing and validating fixes for throttling bugs in HDFS improved system stability and performance."
authors: 
  - shuangliang
tags: ["osre24", reproducibility]
categories: [SoR'24]
date: 2024-09-02
lastmod: 2024-09-02
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

As we reach the conclusion of our ScaleRep project, I want to take a moment to reflect on the journey we’ve undertaken and the significant milestones we’ve achieved. Throughout this project, our primary focus was on identifying, reproducing, and analyzing scalability bugs in cloud systems such as Cassandra, HDFS, and Hadoop. Under the mentorship of Professor Yang Wang and Bogdan “Bo” Stoica, we have gained valuable insights into the complexities of scalability issues and their impact on large-scale distributed systems.

# Key Accomplishments

Over the course of the project, we delved into various aspects of scalability bugs, reproducing some of the most challenging issues faced by cloud systems. One of our notable accomplishments was the successful reproduction and validation of developer fixes for several critical bugs in HDFS. These included:

## 1. Throttling Bugs in HDFS:

We investigated HDFS-17087, where the absence of a throttler in led to unregulated data reads, causing potential performance degradation. By reproducing the bug and applying the developer’s patch, we were able to observe significant improvements in system stability.DataXceiver#readBlock

## 2. Reducing DataNode Load:

HDFS-16386 was another crucial bug we worked on, which involved reducing the load on DataNodes when was working. By analyzing the effects of high CPU and memory usage, we proposed and validated a solution that reduced the number of concurrent threads, ultimately improving the DataNode’s performance.FsDatasetAsyncDiskService

## 3. Improving Log Throttling:

In HDFS-16872, we addressed excessive logging caused by unshared instances of . By making a static member, we were able to share throttling across instances, reducing unnecessary log entries and improving system efficiency.LogThrottlingHelperLogThrottlingHelper

# Insights and Learnings

## 1. Systematic Bug Reproduction: 
One of the most critical aspects of our work was developing a systematic approach to bug reproduction. This involved carefully setting up the environment, applying patches, and validating results through detailed monitoring and analysis. Our reproducible artifacts and investigation scripts will serve as a resource for future researchers and developers.

## 2. Impact of Throttling Mechanisms: 
Our exploration of throttling bugs highlighted the importance of accurate throttling mechanisms in maintaining system performance and stability. Small issues, such as incorrect data rate calculations, can have significant ripple effects on system behavior, emphasizing the need for precise and effective solutions.

## 3. Collaboration and Open Source Contribution: 
Working on an open-source project like ScaleRep underscored the importance of collaboration within the community. The bugs we analyzed and fixed not only improved the systems we worked on but also contributed to the broader effort of enhancing the reliability of cloud systems.



# Conclusion

As we wrap up the ScaleRep project, I am proud of the progress we have made and the contributions we have delivered to the open-source community. The knowledge and experience gained from this project will undoubtedly shape our future endeavors in the field of distributed systems and cloud computing. I am grateful for the guidance and support provided by Professor Yang Wang and Bogdan “Bo” Stoica throughout this journey.

Thank you for following along, and I look forward to continuing to explore the future of scalable and reliable cloud systems!