---
title: "FasTensor/Stream Processing"
authors: [bindong, kwu]
author_notes: ["Research Scientist, Lawrence Berkeley Lab", "Senior Computer Scientist, Lawrence Berkeley Lab"]
tags: ["osre24", "uc", "Streaming Processing"]
date: 2024-01-17
lastmod: 2024-01-17
---

Mentors: Bin Dong, Suren Byna

AIIO (https://github.com/hpc-io/aiio ) revolutionizes the way for users to automatically tune the I/O performance of applications on HPC systems. It currently works on linear regression models but has more opportunities to work on heterogeneous data, such as programming info. This requires extending the linear regression model to  more complex models, such as heterogeneous graph neural networks. The proposed work will include developing the graph neural work-based model to predict the I/O performance and interpretation. 


### Graph Neural Network for I/O Bottleneck Analysis



  * **Topics**: `FasTensor/Streaming Processing`
  * **Skills**:   C++, github
  * **Difficulty**: Difficult
  * **Size**: Large (350 hours)
  * **Mentor**: {{% mention bindong %}}, {{% mention kwu %}}

The Specific tasks of the project include:
- Building a mock workflow based on our DAS application (https://github.com/BinDong314/DASSA) to test stream processing. The mock workflow comprises a data producer, which generates DAS data, and a data consumer, which processes the data.
- Developing a Stream Endpoint (e.g., I/O driver) to iteratively read dynamically increasing data from a directory. The stream endpoint essentially includes open, read, and write functions, and a pointer to remember current file pointer.
- Integrating the Stream Endpoint into the FasTensor library.
- Evaluating the performance of the mock workflow with the new Stream Endpoint.
- Documenting the execution mechanism.



