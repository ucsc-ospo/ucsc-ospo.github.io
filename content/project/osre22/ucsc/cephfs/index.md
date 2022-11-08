---
title: "CephFS"
authors: [admin]
#author_notes: ["Ph.D. Student, UC Santa Cruz"]
tags: ["osre22", "uc"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[CephFS](https://docs.ceph.com/en/latest/cephfs/) is a distributed file system on top of [Ceph](https://ceph.io). It is implemented as a distributed metadata service (MDS) that uses dynamic subtree balancing to trade parallelism for locality during a continually changing workloads. Clients that mount a CephFS file system connect to the MDS and acquire capabilities as they traverse the file namespace. Capabilities not only convey metadata but can also implement strong consistency semantics by granting and revoking the ability of clients to cache data locally.

### CephFS namespace traversal offloading

  * **Topics**: `Ceph`, `filesystems`, `metadata`, `programmable storage`
  * **Skills**: C++, Ceph / MDS
  * **Difficulty**: Medium
  * **Size**: Large (350 hours)
  * **Mentor**: [Carlos Maltzahn](mailto:carlosm@ucsc.edu)

The frequency of metadata service (MDS) requests relative to the amount of data accessed can severely affect the performance of distributed file systems like CephFS, especially for workloads that randomly access a large number of small files as is commonly the case for machine learning workloads: they purposefully randomize access for training and evaluation to prevent overfitting. The datasets of these workloads are read-only and therefore do not require strong coherence mechanisms that metadata services provide by default.

The key idea of this project is to reduce the frequency of MDS requests by offloading namespace traversal, i.e. the need to open a directory, list its entries, open each subdirectory, etc. Each of these operations usually require a separate MDS request. Offloading namespace traversal refers to a client’s ability to request the metadata (and associated read-only capabilities) of an entire subtree with one request, thereby offloading the traversal work for tree discovery to the MDS.

Once the basic functionality is implemented, this project can be expanded to address optimization opportunities, e.g. describing regular tree structures as a closed form expression in the tree’s root, shortcutting tree discovery.
