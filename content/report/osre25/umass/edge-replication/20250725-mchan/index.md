---
title: "Mid-term Blog: Building a Simulator for Benchmarking Replicated Systems"
subtitle: ""
summary: ""
authors: [mchan]
tags: [osre25, reproducibility, distributed systems, edge, coordination protocols]
categories: [SoR]
date: 2025-07-25
lastmod: 2025-07-25
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

Hello there, I'm Michael. In this report, I'll be sharing my progress as part of the [Open Testbed for Reproducible Evaluation of Replicated Systems at the Edges](/project/osre25/umass/edge-replication/) project under the mentorship of {{% mention fadhil %}}.

## About the Project

The goal of the project is to build a _language-agnostic_ interface that enables communication between clients and any consensus protocol such as MultiPaxos, Raft, Zookeeper Atomic Broadcast (ZAB), and others. Currently, many of these protocols implement their own custom mechanisms for the client to communicate with the group of peers in the network. An implementation of MultiPaxos from the [MultiPaxos Made Complete](https://arxiv.org/abs/2405.11183) paper for example, uses a custom Protobuf definition for the packets client send to the MultiPaxos system. With the support of a generalized interface, different consensus protocols can now be tested under the same workload to compare their performance objectively.

## Progress

- **Literature Study:** 
  Reviewed papers and implementations of various protocols including GigaPaxos, Raft, Viewstamped Replication (VSR), and ZAB. Analysis focused on their log replication strategies, fault handling, and performance implications.

- **Development of Custom Protocol:**
  Two custom protocols are currently under development and will serve as initial test subjects for the testbed:
  - A modified GigaPaxos protocol
  - A Primary-Backup Replication protocol with strict log ordering similar to ZAB (logs are ordered based on the sequence proposed by the primary)

  Most of my time has been spent working on the two protocols, particularly on snapshotting and state transfer functionality in the Primary-Backup protocol. Ideally, the testbed should be able to evaluate protocol performance in scenarios involving node failure or a new node being added. In these scenarios, different protocol implementations often vary in their decision of whether to take periodic snapshots or to roll forward whenever possible and generate a snapshot only when necessary.

## Challenges

Early in the project, the initial goal was to benchmark different consensus protocols using arbitrary full-stack web applications as their workload. Different protocols would replicate a full-stack application running inside Docker containers across multiple nodes and the testbed would send requests for them to coordinate between those nodes. In fact, the 2 custom protocols being worked on are specifically made to fit these constraints. 

Developing a custom protocol that supports the replication of a Docker container is in itself already a difficult task. Abstracting away the functionality that allows communicating with the docker containers, as well as handling entry logs and snapshotting the state, is an order of magnitude more complicated.

As mentioned in the [first blog](/report/osre25/umass/edge-replication/20250613-mchan/), an application can be categorized into two types: deterministic and non-deterministic applications. The coordination of these two types of applications are handled in very different ways. Most consensus protocols support only deterministic systems, such as key-value stores and can't easily handle coordination of complex services or external side effects. To allow support for non-deterministic applications would require abstracting over protocol-specific log structures. This effectively restricts the interface to only support protocols that conform to the abstraction, defeating the goal of making the interface broadly usable and protocol-agnostic.

Furthermore, in order to allow **any** existing protocols to support running something as complex as a stateful docker container without the protocol itself even knowing adds another layer of complexity to the system.

## Future Goals

Given these challenges, I decided to pivot to using only key-value stores as the application being used in the benchmark. This aligns with the implementations of most of the existing protocols which typically use key-value stores. In doing so, now the main focus would be to implement an interface that supports HTTP requests from clients to any arbitrary protocols.
