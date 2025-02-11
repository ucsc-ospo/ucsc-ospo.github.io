---
title: "ML-Powered Problem Detection in Chameleon"
authors: [acoskun, msherman]
author_notes: ["Boston University", "University of Chicago"]
tags: ["osre24", "reproducibility", "machine learning", "cloud computing"]
date: 2024-03-06T16:33:57-06:00
lastmod: 2024-03-06T16:33:57-06:00
---

Today’s Continuous Integration/Continuous Development (CI/CD) trends encourage
rapid design of software using a wide range of software components, followed by
frequent updates that are immediately deployed on the cloud. The complexity of
cloud systems along with the component diversity and break-neck pace of
development amplify the difficulty in identifying or fixing problems related to
performance, resilience, and security. Furthermore, existing approaches that
rely on human experts—e.g., methods involving manually-written
rules/scripts—have limited applicability to modern CI/CD processes, as they are
fragile, costly, and often not scalable. Consequently, there is growing
interest in applying machine learning (ML) based methods for identifying
vulnerabilities in code, non-compliant or otherwise problematic software, and
resilience problems in systems and networks. However, despite some success
stories in applying AI for cloud operations (e.g., in resource management),
much of cloud operations still rely on human-centric methods, which require
updates as the cloud undergoes CI/CD cycles. The goal of this summer project is
to explore methods of automation for the Chameleon Cloud to enable faster
detection and diagnosis of problems. Overall, the project will contribute to an
overarching vision of building an infrastructure that collects and synthesizes
cross-layer data from large-scale cloud systems, applying ML-powered methods to
automate cloud ops, and, further, making this data available to researchers
through coherent APIs and analytics engines.

Currently, Chameleon uses runbooks as manual guides for operational tasks,
including routine maintenance and troubleshooting. However, these traditional
runbooks often fall short in dynamic and fast-paced CI/CD environments, as they
lack the flexibility to adapt to changes in software versions, deployment
configurations, and the unique challenges of emerging issues. To overcome these
challenges, the project will leverage ML to automate anomaly detection based on
telemetry data collected from Chameleon Cloud's monitoring frameworks.  This
method will not only facilitate rapid identification of performance anomalies
but also enable automated generation of runbooks. These runbooks can then offer
operators actionable steps to resolve issues efficiently, thereby making the
anomaly mitigation process more efficient. Furthermore, this approach supports
the automatic creation of targeted runbooks for newly generated support
tickets, enhancing response times and system reliability.

Time-permitting, using a collection of automated runbooks (each targeting a
specific problem), we will analyze support tickets, common problems, and their
frequency to offer insights and suggestions to help roadmapping for Chameleon
Cloud to offer the best return on investment on fixing problems.

A key aspect of this summer project is enhancing the reproducibility of
experiments in the cloud and improving data accessibility. We plan to design
infrastructures and APIs so that the telemetry data that is essential for
anomaly detection and automated runbooks is systematically documented and made
available. We also aim to collect and share insights and modules on applying ML
for cloud operations, including ML pipelines, data labeling strategies, data
preprocessing techniques, and feature engineering.  By sharing these insights,
we aim to promote best practices and support reproducible experiments on public
clouds, thus fostering future ML-based practices within the Chameleon Cloud
community and beyond. Time permitting, we will explore applying lightweight
privacy-preserving approaches on telemetry data as well.

- **Topics**: `Machine Learning`, `Anomaly Detection`, `Automated Runbooks`, `Telemetry Data`
- **Skills**:
  - Proficiency in Machine Learning: Understanding of ML algorithms for anomaly detection and automation.
  - Cloud Computing Knowledge: Familiarity with CI/CD environments and cloud architectures.
  - Programming Skills: Proficiency in languages such as Python, especially in cloud and ML contexts.
  - Data Analysis: Ability to analyze telemetry data using data analytics tools and libraries.
- **Difficulty**: Hard
- **Size**: Large
- **Mentors:** {{% mention msherman %}}
