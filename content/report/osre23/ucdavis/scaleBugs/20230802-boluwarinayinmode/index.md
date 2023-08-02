---
title: "ScaleBugs: Reproducible Scalability Bugs"
subtitle: ""
summary:
authors: [boluwarinayinmode, imzahra]
tags: ["osre23"]
categories: ["SummerofReproducibility23"]
date: 2023-08-02
lastmod: 2023-08-02
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

## Introduction

As part of the Scalebugs Project, we have worked on  building a dataset of reproducible scalability bugs. To achieve this, we go through existing bug reports for popular distributed systems, which include Cassandra, HDFS, Ignite, and Kafka. Workloads are designed to reproduce these scalability bugs by triggering some functionalities of the system under different configurations (e.g., different numbers of nodes), for which we will observe the impact on performance. 

So far we have worked on packaging the buggy and fixed versions of scalability systems, a runtime environment that ensures reproducibility, and the workloads used to trigger the symptoms of the bug inside docker containers. By packaging these versions together, we are simplifying the process of deployment and testing. This enables us to switch between different versions efficiently, aiding in the identification and comparison of the bug's behavior. For each scalability system, we have carefully built a runtime environment that is consistent and reproducible. This approach ensures that each time we run tests or investigations, the conditions remain identical.


## New Terms

In order to make sense of the various bug reports, we had to learn some terminologies associated with scalability systems:

**Clusters**: Clusters are groups of related or connected items, often found in various fields such as computer science, data analysis, or even social sciences. For example, in data analysis, clusters might represent groups of data points with similar characteristics, making it easier to understand patterns or trends in the data.

**Cluster Membership**: Cluster membership refers to the process of determining which items or entities belong to a particular cluster. This task can be done based on various criteria, such as similarity in attributes, spatial proximity, or shared characteristics.

**Locks**: In computer programming, locks are mechanisms used to manage access to shared resources, such as files, data structures, or hardware devices. When multiple processes or threads need to access a shared resource simultaneously, locks ensure that only one process or thread can access it at a time, preventing data corruption or conflicts.

**Lock Contentions**: Lock contention occurs when multiple processes or threads attempt to acquire the same lock simultaneously. When this happens, one process or thread must wait until the lock becomes available, leading to potential delays and reduced performance.

**Critical Paths**: In project management or process analysis, a critical path is the longest chain of dependent tasks that determines the overall duration of the project or process. Any delay in tasks along the critical path will directly impact the project's completion time.

**Tokens**: Tokens can have various meanings depending on the context. In computer programming, tokens are the smallest units of source code recognized by a compiler or interpreter. In cryptography, tokens can represent digital certificates or authentication data used for secure communication.

**Nodes**: In the context of network theory or graph theory, nodes are individual points or entities that form a network or graph. In a computer network, nodes can be devices like computers or routers, and in a social network, nodes can represent individuals or entities.

**Peers**: Peers are entities within a network that have the same status or capabilities. In peer-to-peer networks, each node can act as both a client and a server, enabling direct communication between nodes without relying on a central server.

**Gossipers, Gossip Protocol**: In distributed systems, gossipers are nodes that share information with each other using the gossip protocol. The gossip protocol involves randomly selecting peers and exchanging information in a decentralized manner, allowing information to spread quickly across the network.

**Threads**: Threads are the smallest units of execution within a process in computer programming. Multiple threads can run concurrently within a single process, enabling multitasking and parallel processing. Threads can share the same resources within the process, making them more lightweight than separate processes. However, proper synchronization is essential to prevent data corruption or conflicts when multiple threads access shared resources.

**Flush and Writes Contention**: This refers to a situation where simultaneous operations involving data flushing (saving data to a storage medium) and data writing (updating or adding data) are causing conflicts or delays. This contention can arise when multiple processes or threads attempt to perform these operations concurrently, leading to performance bottlenecks or potential data integrity issues.



## Accomplishments
We have been able to build docker containers for the following scalability bugs: 

**IGNITE 12087**

This bug stems from the resolution of the IGNITE-5227 issue (another bug), which has led to a significant decline in the performance of a particular operation. Prior to addressing IGNITE-5227, the insertion of 30,000 entries displayed remarkable efficiency, completing in roughly 1 second. However, post the resolution, executing the same insertion process for 30,000 entries witnessed a considerable slowdown, taking approximately 130 seconds – a performance degradation of nearly 100 times.

**CASSANDRA 14660**

This bug is related to how clusters work together and how a lock is causing conflicts with the critical path. The issue arises from a method call that uses O(Peers * Tokens) resources while contending for a lock, which is causing problems in the write path. The lock is used to protect cached tokens that are essential for determining the correct replicas. The lock is implemented as a synchronized block in the TokenMetadata class.

_How was this fixed?_

It was fixed by reducing the complexity of the operation to O(Peers) taking advantage of some properties of the token list and the data structure.


**CASSANDRA 12281**

This bug is also related to how clusters work together and a lock conflict. The issue arises when a specific method is trying to access a lot of resources (O(Tokens^2)) while contending for a read lock. As reported, a cluster with around 300 nodes has around 300 * 256 (assuming the default number of tokens) tokens, thus joining a new member reportedly is taking more than 30 mins. This happens because due to the long execution time here, this lock makes every gossip message delayed, so the node never becomes active.

_How was this fixed?_

The granularity of the lock is decreased, meaning that the expensive function calls now do not take the problematic read lock and simply use a synchronized block, synchronizing on a specific field, that does the job much better.


**HA16850**

This is a bug related to obtaining thread information in the JvmMetrics package. When obtaining thread information, the original buggy version used MXBeans to obtain thread information. The call uses an underlying native implementation that holds a lock on threads, preventing thread termination or creation. This means that the more threads that we have to obtain information for, the longer the function call will hold a lock. The result is that the execution time scales on the number of active threads O(threads).

_How was this fixed?_

Developers utilized a ThreadGroup to keep track of obtaining metrics for threads. The result is that there is no lock held for every thread.


**CA13923**

This issue revolves around conflicts between the "flush" and "writes" processes. The main problem is that during the "flush" process, a resource-intensive function called "getAddressRanges" is invoked. This function has a high computational cost and its complexity is O(Tokens^2). In other words, the time it takes to complete this function grows quickly as the number of "tokens" increases. This situation is causing challenges and delays in the overall process.

_How was this fixed?_

This function call affected many paths and they made sure no one calls getAddressRanges in critical paths.



## Challenges

**Demanding Memory Requirements**: Running certain builds consumes a significant amount of memory. This places a strain on system resources and can impact the overall performance and stability of the process.

**Little Issues Impacting Execution**: Often, seemingly minor details can obstruct the successful execution of a build. Resolving such issues requires thorough investigation and extensive research into similar problems faced by others in the past.

**Complexities of Scalability Bugs**: Identifying the underlying causes of scalability-related bugs is intricate. These bugs exhibit unique characteristics that can complicate the process of pinpointing and comprehending their root origins.


## What is Docker? ( For those who don't know about it )

Docker is a platform that facilitates the containerization of applications, leading to consistent and efficient deployment across diverse environments. Its benefits include portability, resource efficiency, isolation, and rapid development cycles. DockerHub complements Docker by providing a centralized hub for sharing and accessing container images, fostering collaboration and ease of use within the Docker ecosystem.

More about docker https://docs.docker.com/get-started/overview/


