---
title: "Skyhook Data Management"
authors: ["Jayjeet Chakraborty"]
author_notes: ["Ph.D. Student, UC Santa Cruz"]
tags: ["osre22", "uc", "computational storage"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[SkyhookDM](https://iris-hep.org/projects/skyhookdm.html)


The Skyhook Data Management project extends object storage with data
management functionality for tabular data. SkyhookDM enables storing and query
tabular data in the [Ceph](https://ceph.io) distributed object storage system. It thereby
turns Ceph into an [Apache Arrow](https://arrow.apache.org)-native
storage system, utilizing the Arrow Dataset API to store and query data with server-side data processing, including selection and projection that can significantly reduce the data returned to the client.

SkyhookDM is now part of Apache Arrow (see [blog post](https://arrow.apache.org/blog/2022/01/31/skyhook-bringing-computation-to-storage-with-apache-arrow/)).

-------------------

### Support reading from Skyhook in Dask/Ray using the Arrow Dataset API
  - **Topics**: `Arrow`, `Dask/Ray` 
  - **Skills**: C++ 
  - **Size**: 175 hours
  - **Difficulty:** Medium
  * **Mentor**: [Jayjeet Chakraboorty](mailto:jayjeetc@ucsc.edu)

**Problem:** Dask and Ray are parallel-computing frameworks similar to Apache Spark but in a Python ecosystem. Each of these frameworks support reading tabular data from different data sources such as a local filesystem, cloud object stores, etc. These systems have recently added support for the Arrow Dataset API to read data from different sources. Since, the Arrow dataset API supports Skyhook, we can leverage this capability to offload compute-heavy Parquet file decoding and decompression into the Ceph storage layer. This can help us speed up the queries significantly as CPU will get freed up in the Dask/Ray workers for other processing tasks.

### Implement Gandiva based query executor in SkyhookDM 
  - **Topics**: `Arrow`, `Gandiva`, `SIMD` 
  - **Skills**: C++ 
  - **Size**: 350 hours
  - **Difficulty:** Hard
  * **Mentor**: [Jayjeet Chakraboorty](mailto:jayjeetc@ucsc.edu) 

**Problem:** [Gandiva](https://arrow.apache.org/blog/2018/12/05/gandiva-donation/) allows efficient evaluation of query expressions using runtime code generation using LLVM. The generated code leverages SIMD instructions and is highly optimized for parallel processing in modern CPUs. It is natively supported by Arrow for compiling and executing expressions. SkyhookDM currently uses the Arrow Dataset API (which internally uses Arrow Compute APIs) to execute query expressions inside the Ceph OSDs. Since, the Arrow Dataset API particularly does not support Gandiva currently, the goal of this project is to add support for Gandiva in the Arrow Dataset API in order to accelerate query processing when offloaded to the storage layer. This will help Skyhook combat some of the peformance issues due to the inefficient serialization interface of Arrow.

**References:** 
- https://arrow.apache.org/blog/2018/12/05/gandiva-donation/
- https://www.dremio.com/subsurface/increasing-performance-with-arrow-and-gandiva/
- https://github.com/apache/arrow/tree/master/cpp/src/gandiva

### Add Ability to create and save views from Datasets

  - **Topics**: `Arrow`, `Database views`, `virtual datasets`
  - **Skills**: C++ 
  - **Size**: 175 hours
  - **Difficulty:** Medium
  * **Mentor**: [Jayjeet Chakraboorty](mailto:jayjeetc@ucsc.edu)

Problem - Workloads may repeat the same or similar queries over time. This causes repetition of IO and compute operations, wasting resources.
Saving previous computation in the form of materialized views can provide benefit for future
workload processing.
Solution - Add a method to the Dataset API to create views from queries and save the view as an object in a separate pool with some object key that can be generated from the query that created it.

Reference:
https://docs.dremio.com/working-with-datasets/virtual-datasets.html

-------

### Integrating Delta Lake on top of SkyhookDM

  - **Topics**: `data lakes`, `lake house`, `distributed query processing`
  - **Skills**: C++
  - **NSize**: 175 or 350 hours
  - **Difficulty:** Medium
  * **Mentor**: [Jayjeet Chakraboorty](mailto:jayjeetc@ucsc.edu)

[Delta Lake](https://delta.io/) is a new architecture for querying big data lakes through Spark, providing transactions.
An important benefit of this integration will be to provide an SQL interface for SkyhookDM functionality, through Spark SQL.
This project will further build upon our current work connecting Spark to SkyhookDM through the Arrow Dataset API.
This would allow us to run some of the TPC-DS queries (popular set of SQL queries for benchmarking databases) on SkyhookDM easily.

Reference: [Delta Lake paper] (https://databricks.com/jp/wp-content/uploads/2020/08/p975-armbrust.pdf)
