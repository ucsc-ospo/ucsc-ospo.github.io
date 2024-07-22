---
title: "Exploring Throttling Bugs in HDFS: Reproducing Developer Fixes"
subtitle: 
summary: "Reproducing and validating fixes for throttling bugs in HDFS improved system stability and performance."
authors: 
  - shuangliang
tags: ["osre24", reproducibility]
categories: [SoR'24]
date: 2024-07-22
lastmod: 2024-07-22
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

## HDFS-17087: Missing Throttler in DataXceiver#readBlock

One of the throttling bugs I explored was HDFS-17087. The DataXceiver#readBlock function in HDFS lacked a throttler, resulting in unregulated data reads. This absence could lead to potential performance degradation under heavy loads. The developer fixed this issue by adding a throttler to regulate the data transfer rate. In my work, I reproduced the bug and observed the system's behavior both before and after applying the developer's patch. The results showed a significant improvement in stability and performance post-fix.

![Figure 1](./Figure1.png)


## HDFS-17216: Incorrect Data Rate Calculation

Another crucial bug was HDFS-17216. The issue stemmed from the use of integer division in the getBytesPerSec function, which caused incorrect speed calculations and failed to trigger the throttle, resulting in overspeed. The developer addressed this by switching from integer to float for calculating the elapsed time, ensuring accurate speed measurements. I reproduced the conditions that highlighted the bug's effects and compared the system's performance with and without the fix. The post-fix results confirmed that the throttling mechanism worked correctly, effectively preventing overspeed.

![Figure 2](./Figure2.png)

## Conclusion

Reproducing these throttling bugs and validating the developer fixes was a vital step in understanding their impact on HDFS's scalability. The improvements observed in system stability and performance underscore the importance of accurate throttling mechanisms. This work contributes to the broader effort of maintaining robust and scalable distributed systems, ensuring they can handle increasing loads efficiently.