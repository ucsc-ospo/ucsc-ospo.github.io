---
title: "Evaluating congestion controls past and future" 
authors: [ffund, ashusri]
author_notes: [NYU Tandon School of Engineering]
tags: [osre24, reproducibility, networking, congestion control, TCP, Chameleon, FABRIC]
date: 2024-02-21
lastmod: 2024-02-21
---

- **Topics:** computer networks, congestion control, reproducibility
- **Skills:** Python, Bash scripting, Linux, computer network performance evaluation
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** {{% mention ffund %}} and {{% mention ashusri %}}

**Project Idea Description**

In computer networks, congestion control protocols play an outsize role in determining our experience with networked applications. New congestion control algorithms are regularly proposed by researchers to improve throughput and latency performance, adapt to new types of networks, and align more closely with the needs of new applications.

However, our understanding of the benefits of a new congestion control protocol depends to a large extent on the evaluation - the network topology, the network delay and throughput, the type of flow, the type of competing traffic - and there is no single standard way to evaluate a congestion control protocol. The [Pantheon](https://pantheon.stanford.edu/static/pantheon/documents/pantheon-paper.pdf) project (which is no longer supported) sought to fill this gap somewhat and address the problem of reproducibility of congestion control results, but their approach is not easily adapted to evaluation scenarios representative of new types of applications or networks. Nor is it capable of representing the evaluation scenarios in most published results related to congestion control.

The goal of this project, therefore is to create an evaluation suite for congestion control protocols that can be used to reproduce existing congestion control results in the academic literature, *and* to evaluate new protocols under similar evaluation conditions, *and* to be easily extended to new scenarios. An "evaluation scenario" includes:

* a Python notebook to realize the network topology on the FABRIC and/or Chameleon testbed, and configure the network characteristics,
* scripts to generate the data flow(s) needed for the evaluation,
* and scripts to capture data from the experiment and visualize the results.


**Writing a successful proposal for this project**

To write a good proposal for this project, you should review the most influential papers on TCP congestion control, and especially those related to TCP protocols that are available in the Linux kernel. 

Use your findings to explain what your proposed evaluation suite will include (what network topologies, what flow generators), and justify this with reference to the academic literature. Also indicate which *specific results* you expect to be able to reproduce using this suite (e.g. include figures from influential papers showing evaluation results! with citation, of course).

You can also take advantage of existing open source code that reproduces a congestion control result, e.g. [Replication: When to Use and When Not to Use BBR](https://github.com/sdatta97/imcbbrrepro), or [Some of the Internet may be heading towards BBR dominance: an experimental study](https://github.com/ashutoshs25/bbr-dominance-experiments).

**Github link**

There is no pre-existing Git repository for this project - at the beginning of the summer, the contributor will create a new repository for this project. 

**Project Deliverables**

- "Packages" of evaluation scenarios that can be used to evaluate a congestion control algorithm implemented in the Linux kernel  
- [Trovi](https://chameleoncloud.org/experiment/share/) artifacts for realizing each evaluation scenario on Chameleon






