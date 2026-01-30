---
title: "GeFARe: Discovering Reproducible Failure Scenarios and Developing Failure-Aware Scheduling for Genomic Workflows"
authors: [inkee.kim]
author_notes: ["Associate Professor of School of Computing, University of Georgia"]
tags: [osre25, genomics, "high performance computing (HPC)", "failure characterization", "scientific workflow scheduling", kubernetes]
date: 2025-02-09
lastmod: 2024-02-09
---


- **Topics**: genomic processing (e.g., DNA and RNA alignment), workflow scheduling, resource/cluster management, container orchestration
- **Skills**: Linux, cloud computing (e.g., OpenStack), cluster manager (e.g., Kubernetes), systems automation (e.g., Bash/Python/Puppet), genomic workflows and applications (e.g., BWA, FastQC, Picard, GATK, STAR)
- **Difficulty**: Hard
- **Size**: Large (350 hours)
- **Mentor(s):**  {{% mention inkee.kim %}}


### **Project Idea description**

Large-scale genomic workflow executions require large-scale computing infrastructure, as well as high utilization of that infrastructure, to maximize throughput. Systems researchers have developed various techniques to achieve this goal, including scheduling, resource harvesting, tail mitigation, and failure recovery. However, many of these large-scale efforts have been carried out by separate groups/institutions that operate such large-scale infrastructure (e.g., major tech companies and national research labs). Reproducing and building upon these works at a similar scale in an academic environment is challenging – even labs with strong ties to these institutions often have to rely on trace-based research, which does not fully capture the complexities of real-world deployments. 

We observe two fundamental reasons for this difficulty: 1) a lack of computational infrastructure at a comparable scale and 2) a lack of representative workloads and software stacks. Although the academic community has sought to broaden access to large-scale infrastructure through testbeds like ChameleonCloud and CloudLab, the representative workloads and software stacks to reproduce aforementioned works remain limited.

We aim to address this challenge by providing a robust, easy-to-use, and open-source environment for large-scale genomics workflow scheduling. Specifically, this environment will include: 
	a) a suite of tools to set up infrastructure on academic cloud testbeds,
	b) a scheduling research platform for genomic workflows, and
	c) software stacks to reproduce large-scale failure scenarios. 

We limit the scope of this project to only one or two major failure scenarios. For example, out-of-memory (OOM) failures occur when genomics applications run with insufficient available memory. However, we aim to make the software stack extendable for other scenarios whenever possible.
 
Throughout this project, students will learn to use cloud testbeds (e.g., ChameleonCloud) for workflow scheduling research. They will gain hands-on experience in open-source cluster management and container orchestration tools (e.g., Kubernetes) and will also learn about various aspects of high-performance computing when genomic workflows. 

Finally, we will open-source all the code, software stacks, and datasets created during this project. Using these artifacts, we will also ensure the reproducibility of failure scenarios.



### **Project Deliverable**

- Acquire a basic understanding of genomic data processing (will mentor guidance)
- Build tools to set up a multi-node cluster on ChameleonCloud
- Create automation code/tools to set up genomics workflows’ input and containerized applications
- Discovering failure scenarios for genomics workflow execution (will mentor guidance)
- Develop a Kubernetes-based platform to implement scheduling policies (Students may use or build upon existing open-source works)
- Document the steps needed to reproduce the proposed failure scenarios
