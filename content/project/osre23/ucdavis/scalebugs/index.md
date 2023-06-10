---
title: "ScaleBugs: Reproducible Scalability Bugs"
authors: [rubio, haryadi, hnzhu]
author_notes: ["University of California, Davis", "University of Chicago", "University of California, Davis"]
tags: [osre23, reproducibility, uc, "distributed systems", debugging, hpc, scalability]
date: 2023-02-07
lastmod: 2023-03-29
---

Scalable systems lay essential foundations of the modern information industry. HPC data centers tend to have hundreds to thousands of nodes in their clusters. The use of “extreme-scale” distributed systems has given birth to a new type of bug: scalability bugs. As its name suggests, scalability bugs may be presented depending on the scale of a run, and thus, symptoms may only be observable in large-scale deployments, but not in small or median deployments. For example, [Cassandra-6127](https://issues.apache.org/jira/browse/CASSANDRA-6127) is a scalability bug detected in the popular distributed database Cassandra. The scalability bug causes unnecessary CPU usage, however, the symptom is not observed unless ~1000 nodes are deployed. This demonstrates the main challenge of studying scalability bugs: it is extremely challenging to reproduce without deploying the system at a large scale.  

In this project, our goal is to build a dataset of **reproducible** scalability bugs. To achieve this, we will go through the existing bug reports for popular distributed systems, which include Cassandra, HDFS, Ignite, and Kafka. For each bug report, we determine if the reported bug depends on the scale of the run, such as the number of nodes utilized. With the collected scale-dependent bugs, we then will craft the workload to reproduce those scalability bugs. Our workloads will be designed to trigger some functionalities of the system under different configurations (e.g., different numbers of nodes), for which we will observe the impact on performance. For example, a successful reproduction should be able to show the performance drop along with an increasing number of nodes.

### Building a Dataset of Reproducible Scalability Bugs

  * **Topics**: Scalability systems, bug patterns, reproducibility, bug dataset
  * **Skills**: Linux Shell, Docker, Java, Python
  * **Difficulty**: Medium
  * **Size**: Large (350 hours)
  * **Mentors**: {{% mention rubio %}}, {{% mention haryadi %}}, {{% mention hnzhu %}}  
  * **Contributor(s)**: {{% mention boluwarinayinmode %}}  


The student will build a dataset of reproducible scalability bugs. Each bug artifact in the dataset will contain (1) the buggy and fixed versions of the scalability system, (2) a runtime environment that ensures reproducibility, and (3) a workload shell script that could demonstrate the symptoms of the bug under different scales.

#### Specific Tasks

- Work with the mentors to understand the context of the project.
- Learn the background of scalability systems.
- Inspect the bug reports from Apache JIRA and identify scale-dependent bugs.
- Craft shell scripts to trigger the exact scalability bug described by the bug report.
- Organize the reproducible scalability bugs and write documentation to build the code
and trigger the bug.

