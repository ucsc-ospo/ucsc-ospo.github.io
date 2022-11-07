---
title: "FasTensor"
authors: ["John Wu"]
author_notes: ["Lawrence Berkeley Lab"]
categories: ["osre22"]
tags: ["uc"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[FasTensor](https://sdm.lbl.gov/fastensor/) is a parallel execution engine for user-defined functions on multidimensional arrays.  The user-defined functions follow the stencil metaphor used for scientific computing and is effective for expressing a wide range of computations for data analyses, including common aggregation operations from database management systems and advanced machine learning pipelines.  FasTensor execution engine exploits the structural-locality in the multidimensional arrays to automate data management operations such as file I/O, data partitioning, communication, parallel execution, and so on.

### Continuous Integration

  * **Topics**: `Data Management`, `Analytics`
  * **Skills**:   C++, github
  * **Difficulty**: Medium
  * **Size**: Large (350 hours)
  * **Mentor**: [John Wu](mailto:kwu@lbl.gov), [Bin Dong](mailto:dbin@lbl.gov), [Suren Byna](mailto:sbyna@lbl.gov)

- Develop a test suite for the public API of FasTensor
- Automate execution of the test suite
- Document the continuous integration process
- Develop performance testing suite