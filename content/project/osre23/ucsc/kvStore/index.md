---
title: "Efficient Communication with Key/Value Storage Devices"
authors: [Philip Kufeldt]
author_notes: [Technologist at Seagate]
tags: ["osre23", "uc", performance, "I/O", networking, "key-value", storage]
date: 2022-02-27
lastmod: 2022-02-27
---

Network key value stores are used throughout the cloud as a storage backends (eg AWS ShardStore) and are showing up in devices (eg NVMe KV SSD). The KV clients use traditional network sockets and POSIX APIs to communicate with the KV store. An advancement that has occurred in the last 2 years is a new kernel interface that can be used in lieu of the POSIX API, namely `io_uring`. This new interface uses a set of shared memory queues to provide for kernel-to-user communication and permits zero copy transfer of data. This scheme avoids the overhead of system calls and can improve performance.    

### Implement `io_uring` communication backend

**Topics:** performance, I/O, network, key-value, storage  
**Difficulty:** Medium  
**Size:** Medium or large (120 or 150 hours)  
**Mentors:** [Philip Kufeldt (Seagate)](mailto:philip.kufeldt@seagate.com), [Aldrin Montana (UC Santa Cruz)](mailto:akmontan@ucsc.edu)  

Seagate has been using a network-based KV HDD as a research vehicle for computational storage.  This research vehicle uses open-source user library that implements a KV API by sending network protobuf-based RPCs to a network KV store. Currently it is implemented with the standard socket and POSIX APIs to  communicate with the KV backend.  This project would implement an `io_uring` communication backend and compare the results of both implementations.