---
title: "FasTensor / Stream Processing"
authors: [bindong, kwu]
author_notes: ["Research Scientist, Lawrence Berkeley Lab", "Senior Computer Scientist, Lawrence Berkeley Lab"]
tags: ["osre24", "uc", "Streaming Processing"]
date: 2024-01-17T10:15:56-07:00
lastmod: 2024-01-17T10:15:56-07:00
---

[FasTensor] (https://github.com/BinDong314/FasTensor) is a generic tensor processing engine with scalability from single nodes to thousands of nodes on HPC.  FasTensor supports applications from traditional SQL query to complex DFT solver in scientific applications. It has a 1000X performance advantage over MapReduce and Spark in supporting generic data processing functions on tensor structure. In this project, we propose to expand FasTensor with streaming functionality to support online data processing. Specifically, participants of this project will develop a stream endpoint for retrieving live data output from applications, such as DAS. The stream endpoint performs the function to maintain the pointer of data, which could be a n-dimensional subset of a tensor.  

### FasTensor / Stream Processing

- **Topics**: `FasTensor/Streaming Processing`
- **Skills**:   C++, github
- **Difficulty**: Difficult
- **Size**: Large (350 hours)
- **Mentor**: {{% mention bindong %}}, {{% mention kwu %}}

The Specific tasks of the project include:
- Building a mock workflow based on our DAS application (https://github.com/BinDong314/DASSA) to test stream processing. The mock workflow comprises a data producer, which generates DAS data, and a data consumer, which processes the data.
- Developing a Stream Endpoint (e.g., I/O driver) to iteratively read dynamically increasing data from a directory. The stream endpoint essentially includes open, read, and write functions, and a pointer to remember current file pointer.
- Integrating the Stream Endpoint into the FasTensor library.
- Evaluating the performance of the mock workflow with the new Stream Endpoint.
- Documenting the execution mechanism.
