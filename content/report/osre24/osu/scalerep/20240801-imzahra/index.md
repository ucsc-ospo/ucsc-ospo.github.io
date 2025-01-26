---
title: "[MidTerm] ScaleRep: Reproducing and benchmarking scalability bugs hiding in cloud systems"
summary:
authors: ["imzahra"]
tags: ["osre24", "reproducibility", "scalability"]
categories: ["SummerofReproducibility24"]
date: 2024-08-01
lastmod: 2024-08-01
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Tackling scalability bugs in large-scale distributed systems"
  focal_point: Center
  preview_only: false
---

Hey there, scalability enthusiasts and fellow researchers! I’m excited to share my progress on the [ScaleRep project](/project/osre24/osu/scalerep/) for SoR 2024 under the mentorship of {{% mention bogdanstoica %}} and {{% mention wang.7564 %}}. Here’s a glimpse into how we’re tackling scalability bugs in large-scale distributed systems.

## Project Overview

Large-scale distributed systems are the backbone of modern computing, powering various applications and services. However, these systems often face challenges related to reliability and performance, particularly scalability bugs. These bugs manifest in large-scale deployments, causing issues such as system downtime, reduced responsiveness, and data loss. Traditional bug-finding methods fall short in detecting these bugs, which are triggered by factors like component count, system load, workload size, recovery protocol reliability, and intermediate failure magnitude.

Our project, ScaleRep, aims to address these challenges by analyzing recent scalability issues from ten popular open-source large-scale systems. We are providing detailed accounts of bug reproduction experiences, identifying common challenges, and developing protocols for triggering and quantifying the impact of scalability bugs.

## Progress Highlights

So far, I have been working on the following bugs and have successfully uploaded some of them to Trovi. Here’s a brief overview of my progress:

### Bugs Worked On:
1. **[IGNITE-20614](https://issues.apache.org/jira/browse/IGNITE-20614)**: Uploaded to Trovi [Trovi Link](https://www.chameleoncloud.org/experiment/share/9f045059-011e-4089-90d4-0f5845ef3c73)
2. **[IGNITE-17407](https://issues.apache.org/jira/browse/IGNITE-17407)**: Uploaded to Trovi [Trovi Link](https://www.chameleoncloud.org/experiment/share/9cfd42b7-c7c9-4b6b-a538-b6c496eb1bed)
3. **[IGNITE-20692](https://issues.apache.org/jira/browse/IGNITE-20692)**
4. **[IGNITE-16600](https://issues.apache.org/jira/browse/IGNITE-16600)**
5. **[IGNITE-16072](https://issues.apache.org/jira/browse/IGNITE-16072)**

## What is Chameleon and Trovi?

**[Chameleon](https://chameleoncloud.org/)** is a configurable experimental environment for large-scale cloud research. It provides a platform for running and testing distributed systems at scale, allowing researchers to reproduce and study scalability issues in a controlled setting.

**[Trovi](https://chameleoncloud.org/experiment/share/)** is a platform that facilitates the sharing of reproducible artifacts. By uploading our bug reproduction artifacts to Trovi, we enable other researchers to easily reproduce scalability bugs, fostering collaboration and advancing the field of distributed systems research.

## Short Description of the Bugs

1. [IGNITE-20614](https://issues.apache.org/jira/browse/IGNITE-20614)
This bug refers to an issue where the Ignite service grid experiences degradation or hangs under specific conditions related to service deployment and node restarts.

**Root Causes**: The root cause is a race condition during the deployment and undeployment of services in the service grid, particularly when nodes are restarted or when there is a significant amount of concurrent service deployment and undeployment activity.

**Impact**: The impact of this bug includes potential service grid hangs, degraded performance, and possible inability to deploy or undeploy services as expected, which can disrupt the overall operation of the Ignite cluster.

**Fix**: The fix involves adding proper synchronization mechanisms to handle concurrent service deployment and undeployment operations more gracefully, ensuring that race conditions are avoided.

2. [IGNITE-17407](https://issues.apache.org/jira/browse/IGNITE-17407)
This issue pertains to the incorrect behavior of the Ignite thin client protocol, particularly when dealing with binary objects and schema changes.

**Root Causes**: The root cause lies in the way the thin client handles binary object schema changes. The thin client was not correctly updating the schema cache, leading to inconsistencies and incorrect behavior when deserializing binary objects.

**Impact**: Users of the thin client may experience issues with binary object deserialization, leading to potential data corruption, incorrect query results, and overall application instability.

**Fix**: The fix involves updating the thin client protocol to properly handle schema changes by ensuring that the schema cache is correctly updated and synchronized with the server.

3. [IGNITE-20692](https://issues.apache.org/jira/browse/IGNITE-20692)
This bug is related to the performance degradation observed in the Ignite SQL engine when executing certain complex queries.

**Root Causes**: The root cause is identified as inefficient query planning and execution strategies for specific types of complex SQL queries, leading to excessive resource consumption and slow query performance.

**Impact**: Users running complex SQL queries may experience significant performance degradation, leading to slower response times, increased CPU and memory usage, and potentially impacting the overall performance of the Ignite cluster.

**Fix**: The fix involves optimizing the SQL query planner and executor to handle complex queries more efficiently, including better indexing strategies, improved query plan caching, and more effective resource management during query execution.

4. [IGNITE-16600](https://issues.apache.org/jira/browse/IGNITE-16600)
This bug involves an issue with speed-based throttling in the checkpoint process, leading to possible starvation of the checkpoint thread under heavy load.

**Root Causes**: The root cause is the absence of proper mechanisms to wake up throttled threads when they no longer need to be throttled, resulting in unnecessary waiting and potential starvation of the checkpoint thread.

**Impact**: Under heavy load, the checkpoint process can be significantly delayed, leading to slower checkpoint completion times, increased risk of data loss, and overall degraded performance of the Ignite cluster.

**Fix**: The fix includes implementing methods to wake up throttled threads when they no longer need to be throttled (tryWakeupThrottledThreads and shouldThrottle), ensuring that the checkpoint process can proceed without unnecessary delays.

5. [IGNITE-16072](https://issues.apache.org/jira/browse/IGNITE-16072)
This issue pertains to the incorrect handling of SQL queries involving NULL values in the Ignite SQL engine, leading to unexpected query results.

**Root Causes**: The root cause is an incorrect implementation of SQL semantics for handling NULL values in certain query conditions, particularly in the presence of complex joins and subqueries.

**Impact**: Users may experience incorrect query results when NULL values are involved, leading to potential data inconsistencies and incorrect application behavior.

**Fix**: The fix involves correcting the SQL engine's implementation to properly handle NULL values according to the SQL standard, ensuring that queries involving NULL values produce the expected results.

## What's Next?

#### Continued Bug Reproduction:
- Focus on reproducing more scalability bugs

#### Documentation of Challenges:
- Breakdown specific challenges encountered during attempts to reproduce scalability bugs.
- Categorize challenges, including technical complexities, environmental dependencies, and lack of documentation in bug reports.

#### Finalizing Project Deliverables:
- Package artifacts using Jupyter notebook scripts for convenient replay of investigation steps.
- Upload the package to Trovi for replayable artifacts, enabling other researchers to easily reproduce scalability bugs for our benchmark applications.

### Conclusion

The ScaleRep project has made significant strides in reproducing and benchmarking scalability bugs in large-scale distributed systems. By successfully reproducing and documenting scalability bugs, we are contributing valuable insights to the research community, aiding in the development of more robust distributed systems. The protocols and methodologies devised in this project will serve as valuable tools for researchers exploring similar issues.

Stay tuned for more updates as we continue to tackle scalability bugs and improve the reliability and performance of large-scale distributed systems.
