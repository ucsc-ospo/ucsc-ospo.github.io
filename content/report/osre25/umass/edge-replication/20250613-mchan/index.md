---
title: "Building a Simulator for Benchmarking Replicated Systems"
# subtitle: "Since OSRE 2023 we ask student contributors to blog!"
summary: "This is now common practice and an efficient way to track activities within OSRE projects. Include links to proposals, presentations, reports, and experience."
authors: [mchan]
tags: [osre25, reproducibility, distributed systems, edge, coordination protocols]
categories: []
date: 2025-06-14
lastmod: 2025-06-14
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [osre]
---

Hi, I'm Michael. I'm currently contributing to the [Open Testbed for Reproducible Evaluation of Replicated Systems at the Edges](/project/osre25/umass/edge-replication/) under the mentorship of {{% mention fadhil %}}. You can find more details on the project proposal [here](https://drive.google.com/file/d/1LQCPu1h9vXAbdL6AX_E9S43dsIOndTyW/view?usp=sharing).

What we are trying to achieve is to create a system to test and evaluate the performance of different consensus protocols and consistency models under the same application and workload. The consensus protocols and consistency models are both tested on various replicated black-box applications. Essentially, the testbed itself is able to deploy any arbitrary stateful application on multiple machines (nodes) as long as it is packaged in the form of a docker image. The consensus protocol is used to perform synchronization between the stateful part of the application (in most cases, the database). The goal is that by the end of this project, the testbed we are building has provided the functionality and abstraction to support the creation of new consensus protocols to run tests on.

One major challenge in implementing this is with regards to the handling of replication on the running docker containers. Generally, the services that can be deployed in this system would be of two types:
1. A Deterministic Application (An application that will always return the same output when given the same input. e.g., a simple CRUD app)
2. A Non-Deterministic Application (An application that may return the different outputs when given the same input. e.g., an LLM which may return different response from the same prompt request)

Both of these application types requires different implementation of consensus protocols. In the case of a deterministic application, since all request will always yield the same response (and the same changes inside the database of the application itself), the replication protocol can perform replication on the request to all nodes. On the other hand, in a non-determinisitic application, the replication protocol applies synchronization on the state of the database directly since a different response may be returned on the same request.
