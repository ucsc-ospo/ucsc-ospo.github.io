---
title: "Adaptive Load Balancers for Low-latency Multi-hop Networks"
authors: ["Katia Obraczka"]
author_notes: ["Professor of Electrical and Computer Engineering, UC Santa Cruz"]
tags: ["osre22", "uc", "networking", "distributed systems"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

This project aims at designing efficient, adaptive link level load balancers for networks that handle different kinds of traffic, in particular networks where flows are heterogeneous in terms of their round trip times. Geo distributed data centers are one such example. With the large-scale deployments of 5G in the near future, there will be even more applications, including more bulk transfers of videos and photos, augmented reality applications and virtual reality applications which take advantage of 5G’s low latency service. With the development and discussion about Web3.0 and Metaverse, the network workloads across data centers are only going to get more varied and challenging. All these add to heavy, bulk of data being sent to the data centers and over the backbone network. These traffic have varying quality of service requirements, like low latency, high throughput and high definition video streaming. Wide area network (WAN)  flows are typically data heavy tasks that consist of backup data taken for a particular data center. The interaction of the data center and WAN traffic creates a very interesting scenario with its own challenges to be addressed. WAN and data center traffic are characterized by differences in the link utilizations and round trip times. Based on readings and literature review, there seems to be very little work on load balancers that address the interaction of data center and WAN traffic. This in turn motivates the need for designing load balancers that take into account both WAN and data center traffic in order to create high performance for more realistic scenarios.  This work proposes a load balancer that is adaptive to the kind of traffic it encounters by learning from the network conditions and then predicting the optimal route for a given flow. 

Through this research we seek to contribute the following : 
- Designing a load balancer, that is adaptive to datacenter and WAN traffic, and in general can be adapted to varied traffic conditions
- Real time learning of the network setup and predicting optimal paths
- Low latency, high throughput and increased network utilization deliverables 

### Adaptive, Dynamic Load Balancing for data center and WAN traffic 

- **Topics:** 'data center networking', TCP/IP stack', 'congestion control', 'load balancing' 
- **Skills:** C++, python, linux ; experience with network simulators would be helpful
- **Difficulty:** moderate/ challenging 
- **Size**: Medium or Large (175 or 350 hours) 
- **Mentors:** [ Katia Obraczka](mailto:katia@soe.ucsc.edu),[Abdul Kabbani](mailto:akabbani@gmail.com), [Lakshmi Krishnaswamy](mailto:lakrishn@ucsc.edu)

Specific tasks:
- Understanding the OMNeT++ network simulator and creating simple networks and data center topologies to understand the simulation environment.  
- Implementing existing load balancers on OMNeT++ and exploring the effect of different features of the load balancers with data center traffic and WAN traffic.
- Finding and testing out WAN specific traffic that may exist, like video streaming traffic, large database queries etc. 
- Working with the mentors on developing a learning-based load balancer framework that learns from past sample traffic, network conditions, to adapt dynamically to current network conditions. 
