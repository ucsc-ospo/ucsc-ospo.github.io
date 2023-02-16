---
title: "FasTensor"
authors: ["John Wu"]
author_notes: ["Lawrence Berkeley Lab"]
tags: ["osre23", "uc", "data management", "data science"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[FasTensor](https://sdm.lbl.gov/fastensor/) is a parallel execution engine for user-defined functions on multidimensional arrays.  The user-defined functions follow the stencil metaphor used for scientific computing and is effective for expressing a wide range of computations for data analyses, including common aggregation operations from database management systems and advanced machine learning pipelines.  FasTensor execution engine exploits the structural-locality in the multidimensional arrays to automate data management operations such as file I/O, data partitioning, communication, parallel execution, and so on.

### Tensor execution engine on GPU

  * **Topics**: `Data Management`, `Analytics`
  * **Skills**:   C++, github
  * **Difficulty**: Difficult
  * **Size**: Large (350 hours)
  * **Mentor**: [John Wu](mailto:kwu@lbl.gov), [Bin Dong](mailto:dbin@lbl.gov), [Suren Byna](mailto:sbyna@lbl.gov)

Tensor based computing is needed by scientific applications and now advanced AI model training. Most tensor libraries are hand customized and optimized on GPU,  and most of  they only serve one kind of application. For example, TensorFlow is only optimized for AI model training.  Optimizing generic tensor computing libraries on GPU can benefit wide applications. Our FasTensor,  as a generic tensor computing library, can only work efficiently on CPU now.  How to run the FasTensor on GPU is still none-explored work. Research and development challenges will include but not limited to: 1) how to maintain structure-locality of tensor data on GPU; 2) how to reduce the performance loss when the structure-locality of tensor is broken on GPU.
  
- Develop a mechanism to move user-define computing kernels onto GPU
- Evaluate the performance of the execution engine
- Document the execution mechanism
- Develop performance testing suite

### Continuous Integration

  * **Topics**: `Data Management`, `Analytics`
  * **Skills**:   C++, github
  * **Difficulty**: Medium
  * **Size**: Large (300 hours)
  * **Mentor**: [John Wu](mailto:kwu@lbl.gov), [Bin Dong](mailto:dbin@lbl.gov), [Suren Byna](mailto:sbyna@lbl.gov)

- Develop a test suite for the public API of FasTensor
- Automate execution of the test suite
- Document the continuous integration process
