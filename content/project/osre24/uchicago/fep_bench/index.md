---
title: "FEP-Bench: Benchmarking for Enhanced Feature Engineering and Preprocessing in Machine Learning" 
authors: [yuyangh, swami]
author_notes: [PhD Student at the University of Chicago, Senior Manager at IBM]
tags: [osre24, reproducibility, "storage systems", machine learning"]
date: 2024-06-03
lastmod: 2024-06-03
---

**Project Idea Description**

- **Topics:** Storage systems, machine learning
- **Skills:** Python, PyTorch, Bash scripting, Linux, Machine Learning modeling 
- **Difficulty:** Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention yuyangh %}} (primary contact), {{% mention swami %}}
- **Contributor(s):** {{% mention jaycezhu %}}


In the realm of machine learning (ML), preprocessing of data is a critical yet often underappreciated phase, consuming approximately 80% of the time in common ML tasks. This extensive time consumption can be attributed to various challenges encountered from both data and computation perspectives.

From the data side, one significant challenge is the slow retrieval of data from data lakes, which are storage repositories that hold a vast amount of raw data in its native format. However, the process of extracting this data can be slow, causing computation cycles to wait for data arrival and leading to delays in the entire preprocessing phase. Furthermore, the size of the data often exceeds the memory capacity of standard computing systems. This is a frequent occurrence in ML, as datasets are typically large and complex. Handling such large datasets requires sophisticated memory management techniques to ensure efficient preprocessing without overwhelming the system's memory.

On the computation side, a naive solution to data operations, especially aggregation, often leads to inefficiencies. These operations may require grouping a large chunk of data as a prerequisite before performing any actual computation. This grouping, without careful configuration and management, can trigger serious data shuffling, leading to extensive remote data movement when the data is distributed across various storage systems. Such data movement is not only time-consuming but also resource-intensive.

To mitigate these challenges, there is a pressing need to design better caching, prefetching, and heuristic strategies for data preprocessing. The team aims to significantly reduce the time and resources required for preprocessing by optimizing data retrieval and computational processes.

However, prior to the design and implementation of such a system, a systematic understanding of the preprocessing workflow is essential. Hence, throughout the program, the students will need to:
- Understand the current system used to preprocess data for ML training, for example, Hadoop or Spark.
- Collect the common datasets used for different types of ML models.
- Collect the typical operations used for preprocessing these datasets.
- Benchmark the performance in these operations under the existing frameworks under various experimental settings.
- Package the benchmark such that the team can later use it for reproduction or evaluation.

**Project Deliverable**
- A rolodex for the commonly used dataset and corresponding preprocess operations and expected output formats/types
- A Chameleon Trovi package that preprocess the dataset with single-machine preprocessing framework like pandas
- A Chameleon Trovi package that preprocess the dataset in an existing distributed computation framework like Hadoop or Spark

