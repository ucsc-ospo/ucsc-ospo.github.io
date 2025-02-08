---
title: "Seam: Kubernetes-Aware Programmable Networking & Cloud Provisioning"
authors: [mfsada]
author_notes: ["Researcher, UC San Diego"]
tags: ["osre25", "uc", "web development", "educational technologies", "ucsd", "sdsc", "kubernetes", "smartnics", "networks"]
date: 2025-02-05
lastmod: 2025-02-05
---

Seam is a project focused on building a Kubernetes-aware programmable networking and cloud provisioning system. It combines Python, Kubernetes, P4 programming, and SmartNICs to create a robust framework for managing cloud resources, optimizing networking, and provisioning virtual machines. Students will learn about cutting-edge technologies such as Kubernetes, Docker, P4 programming, SmartNICs, KubeVirt, Prometheus, Grafana, and Flask, while working on real-world applications in high-performance computing environments. This project will help students understand the intricacies of cloud resource management and programmable networking, providing them with valuable skills for future careers in software engineering, networking, and DevOps.

The project involves creating a **Python library** for provisioning Kubernetes resources, including virtual machines and networking, using tools such as **KubeVirt** for VM provisioning and **ESnet SENSE** for network configuration. The library will also integrate monitoring solutions with **Prometheus** and **Grafana** for real-time metrics collection and visualization. Students will develop **Flask-based dashboards** for managing these resources, implement automated pipelines using **GitLab CI/CD**, and explore full-stack web development, database management with **PostgreSQL**, and API design.

In addition, students will gain hands-on experience with **programmable networking** using **P4** and **SmartNICs**, learning how to write P4 programs for dynamic routing, security, and network policy enforcement at the hardware level. The integration of **Kubernetes**, **SmartNICs**, and **P4 programming** will allow for advanced optimizations and efficient management of high-performance cloud environments.

Thus far, the framework has been developed to allow provisioning of resources within Kubernetes, integrating Prometheus and Grafana for monitoring, and providing an interface for users to manage cloud resources. We aim to extend this by incorporating advanced network policies and improving the web interface.

### Seam / Kubernetes Resource Provisioning and Management

The proposed work includes expanding the Python library to support comprehensive **Kubernetes resource provisioning**, **network management**, and **virtual machine provisioning** using **KubeVirt**. Students will enhance the current implementation to allow users to define **resource limits, CPU/GPU quotas, and network policies**. They will also integrate with **ESnet SENSE** to facilitate **L2 networking**, and explore the use of **Prometheus** and **Grafana** for real-time performance monitoring and metrics collection.

- **Topics:** Kubernetes, Python, Cloud Computing, Networking, Programmable Networking, Monitoring, CI/CD
- **Skills:** Python, Kubernetes, P4 programming, KubeVirt, ESnet SENSE, Docker, GitLab CI/CD, Prometheus, Grafana, PostgreSQL, Flask
- **Difficulty:** Hard
- **Size:** Large (400 hours)
- **Mentors:** {{% mention "mfsada" %}}

### Seam / Full-Stack Web Development and Dashboard

The proposed work includes building a **Flask-based web dashboard** using **Bootstrap** for UI, integrating it with the **Python library** to enable users to easily provision resources, monitor network performance, and track resource usage in real-time. The dashboard will support **role-based access control (RBAC)**, allowing for secure multi-user management. Students will also integrate **PostgreSQL** for managing and storing configurations, logs, and performance metrics.

- **Topics:** Full-Stack Web Development, Flask, Bootstrap, PostgreSQL, Kubernetes, Monitoring, DevOps
- **Skills:** Web Development, Flask, Bootstrap, PostgreSQL, API Development, Kubernetes
- **Difficulty:** Medium to Hard
- **Size:** Medium (300 hours)
- **Mentors:** {{% mention "mfsada" %}}

### Seam / CI/CD and GitLab Integration

The proposed work includes setting up **GitLab CI/CD pipelines** for automated **testing, deployment**, and **maintenance** of the Python library, Kubernetes resources, and web dashboard. Students will automate the deployment of **P4 programs**, **Kubernetes deployments**, and **networking configurations**. They will also focus on **unit testing, integration testing**, and the **automation of benchmarking experiments** to ensure reproducibility of results.

- **Topics:** CI/CD, GitLab, Python, Kubernetes, DevOps, Testing, Automation
- **Skills:** GitLab CI/CD, Python, Kubernetes, Docker, Automation, Testing, Benchmarking
- **Difficulty:** Medium to Hard
- **Size:** Medium (300 hours)
- **Mentors:** {{% mention "mfsada" %}}

### Seam / Networking & SmartNIC Programming

The proposed work includes writing **P4 programs** to control network traffic flow, enforce network security policies, and optimize data transfer across the Kubernetes cluster. Students will gain experience with **SmartNICs** (Xilinx Alveo U55C, SN1000, NVIDIA Bluefield 2) and **Tofino switches**, using P4 to write **network policies** and integrate with the **Kubernetes network layer** (Multus, Calico). Students will also explore **gRPC APIs** for dynamically adjusting network policies and provisioning virtual network interfaces in real time.

- **Topics:** Networking, P4 Programming, SmartNICs, Kubernetes Networking, Cloud Computing
- **Skills:** P4, Networking, SmartNICs, Kubernetes Networking, Multus, Calico, gRPC
- **Difficulty:** Hard
- **Size:** Large (400 hours)
- **Mentors:** {{% mention "mfsada" %}}


