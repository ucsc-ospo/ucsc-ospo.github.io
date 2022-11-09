---
title: "HDF5"
authors: ["Suren Byna", "Houjun Tang"]
author_notes: ["Lawrence Berkeley Lab", "Lawrence Berkeley Lab"]
tags: ["osre22", "uc", "storage systems"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[HDF5](https://portal.hdfgroup.org/display/knowledge/What+is+HDF5) is a unique technology suite that makes possible the management of extremely large and complex data collections.

The HDF5 technology suite includes:
  * A versatile data model that can represent very complex data objects and a wide variety of metadata.
  * A completely portable file format with no limit on the number or size of data objects in the collection.
  * A software library that runs on a range of computational platforms, from laptops to massively parallel systems, and implements a high-level API with C, C++, Fortran 90, and Java interfaces.
  * A rich set of integrated performance features that allow for access time and storage space optimizations.
  * Tools and applications for managing, manipulating, viewing, and analyzing the data in the collection.

### Python Interface to HDF5 Asynchronous I/O

  * **Topics**: `Python`, `Async I/O`, `HDF5`
  * **Skills**: Python, C, HDF5
  * **Difficulty**: Medium
  * **Size**: Large (350 hours)
  * **Mentor**: [Suren Byna](mailto:sbyna@lbl.gov), [Houjun Tang](mailto:htang4@lbl.gov)

HDF5 is a well-known library for storing and accessing (known as "Input and Output" or I/O) data on high-performance computing systems. Recently, new technologies, such as asynchronous I/O and caching, have been developed to utilize fast memory and storage devices and to hide the I/O latency. Applications can take advantage of an asynchronous interface by scheduling I/O as early as possible and overlapping computation with I/O operations to improve overall performance. The existing HDF5 asynchronous I/O feature supports the C/C++ interface. This project involves the development and performance evaluation of a Python interface that would allow more Python-based scientific codes to use and benefit from the asynchronous I/O.

