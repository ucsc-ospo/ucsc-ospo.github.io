---
title: "NETAI: AI-Powered Network Anomaly Detection and Diagnostics Platform"
authors: [dmishin, dweitzel]
author_notes: ["Researcher, UC San Diego"]
tags: ["osre26", "uc", "web development", "educational technologies", "ucsd", "sdsc", "kubernetes", "llm", "ai", "network diagnostics", "perfsonar", "nrp"]
date: 2026-02-05
lastmod: 2026-02-05
---

NETAI (Network AI) is an AI-powered network anomaly detection and diagnostics platform for the National Research Platform (NRP). This project combines Kubernetes-native LLM integration, network performance monitoring, and predictive analytics to create an intelligent assistant for network operators. Students will work with cutting-edge technologies including Large Language Models (LLMs), Kubernetes, perfSONAR network measurements, time-series analysis, and containerized AI/ML workloads, while contributing to real-world applications in network operations and diagnostics.

The project involves developing a **Kubernetes chatbot** that leverages NRP's managed LLM service (providing access to models like Qwen3-VL, GLM-4.7, and GPT-OSS) to help network operators understand complex network behaviors, diagnose anomalies, and receive natural language explanations of network issues. Students will integrate perfSONAR measurement data with traceroute path analysis to create an interactive network topology visualization, and develop **AI/ML models** for predictive network performance analysis using NRP's GPU resources.

In addition, students will gain hands-on experience with **fine-tuning LLMs** on historical network diagnostics data, developing **time-series forecasting models** for network metrics, and implementing **anomaly detection** using deep learning techniques. The entire AI/ML pipeline will be containerized and deployed as Kubernetes workloads, utilizing GPU-enabled pods for model training and inference, ensuring scalability and seamless integration with existing NRP infrastructure.

The platform builds upon existing network diagnostics capabilities, combining end-to-end throughput measurements with detailed traceroute data to enable operators to visualize network paths, identify performance bottlenecks, and understand relationships between metrics and underlying infrastructure. The AI enhancement will provide predictive capabilities, automated incident reporting, and intelligent recommendations for network remediation strategies.

### NETAI / LLM Integration & Kubernetes Chatbot

The proposed work includes developing a **Kubernetes-native chatbot** that integrates with NRP's managed LLM service to provide intelligent network diagnostics assistance. Students will create a conversational interface that can answer questions about network performance, explain anomalies in natural language, and suggest remediation strategies. They will fine-tune LLMs on historical network diagnostics data, test results, and traceroute information to create domain-specific assistants. Students will implement **RESTful APIs** for chatbot interactions, develop **prompt engineering** strategies for network diagnostics, and create **context-aware responses** that incorporate real-time network telemetry. The chatbot will be deployed as Kubernetes services, utilizing GPU pods for inference and integrating with the existing diagnostics platform.

- **Topics:** Large Language Models, Kubernetes, Chatbots, Natural Language Processing, Network Diagnostics, API Development
- **Skills:** Python, Kubernetes, LLM APIs (Qwen3-VL, GLM-4.7, GPT-OSS), Prompt Engineering, REST APIs, Docker, GPU Computing
- **Difficulty:** Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "dmishin" %}}, {{% mention "dweitzel" %}}

### NETAI / Network Anomaly Detection Models

The proposed work includes developing **deep learning models** for network anomaly detection using historical perfSONAR and traceroute data. Students will create models that can identify slow links, high packet loss, excessive retransmits, and failed network tests automatically. They will implement **anomaly detection algorithms** using techniques such as autoencoders, LSTM networks, and transformer architectures. Students will train models on NRP's GPU clusters using historical network telemetry stored in SQLite databases, develop **feature engineering** pipelines for network metrics, and create **real-time inference services** deployed as Kubernetes workloads. The models will be integrated into the diagnostics platform to provide automated anomaly detection alongside the interactive visualization.

- **Topics:** Deep Learning, Anomaly Detection, Time-Series Analysis, Network Monitoring, Model Training, GPU Computing
- **Skills:** Python, PyTorch/TensorFlow, scikit-learn, Pandas, NumPy, SQLite, Kubernetes, GPU Pods, MLOps
- **Difficulty:** Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "dmishin" %}}, {{% mention "dweitzel" %}}

### NETAI / Predictive Analytics & Forecasting

The proposed work includes developing **predictive models** that can forecast network performance degradation and identify patterns in network anomalies before they impact users. Students will create **time-series forecasting models** for network metrics such as throughput, latency, and packet loss, using techniques like ARIMA, Prophet, and deep learning-based forecasting. They will implement **few-shot learning approaches** to adapt models to new network topologies and measurement patterns, develop **early warning systems** for potential network issues, and create **automated incident report generation** using LLMs. Students will leverage NRP's GPU resources for training forecasting models and deploy them as Kubernetes services for real-time predictions integrated with the diagnostics dashboard.

- **Topics:** Time-Series Forecasting, Predictive Analytics, Machine Learning, Network Performance, Early Warning Systems, LLM Integration
- **Skills:** Python, PyTorch/TensorFlow, Prophet, ARIMA, Pandas, NumPy, Time-Series Analysis, Kubernetes, GPU Computing
- **Difficulty:** Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "dmishin" %}}, {{% mention "dweitzel" %}}

### NETAI / Kubernetes Deployment & Infrastructure

The proposed work includes setting up **Kubernetes-based infrastructure** for deploying the entire NETAI platform, including LLM services, ML models, and the diagnostics dashboard. Students will create **Helm charts** for deploying containerized AI/ML workloads, configure **GPU-enabled pods** for model training and inference, and implement **persistent storage** solutions for maintaining historical network telemetry. They will develop **GitLab CI/CD pipelines** for automated testing and deployment, set up **monitoring and observability** using Prometheus and Grafana for tracking model performance and resource usage, and create **scalable deployment strategies** that leverage NRP's distributed computing resources. Students will also integrate the platform with existing perfSONAR infrastructure and ensure seamless operation within the NRP cluster.

- **Topics:** Kubernetes, DevOps, CI/CD, GPU Computing, Container Orchestration, Infrastructure as Code, Monitoring
- **Skills:** Kubernetes, Helm, GitLab CI/CD, Prometheus, Grafana, Docker, GPU Pods, Persistent Storage, Infrastructure Automation
- **Difficulty:** Medium to Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "dmishin" %}}, {{% mention "dweitzel" %}}

## Project Resources

- **National Research Platform**: https://nrp.ai/
- **NRP LLM Service**: https://nrp.ai/documentation/userdocs/ai/llm-managed/
- **perfSONAR**: https://www.perfsonar.net/
- **MaDDash**: https://github.com/esnet/maddash
- **Network Monitoring Documentation**: https://nrp.ai/documentation/

## Background

This project addresses critical gaps in network performance monitoring for the National Research Platform by integrating AI/ML capabilities with existing perfSONAR-based diagnostics. The platform combines end-to-end network measurements with detailed path-level analysis, enhanced by intelligent AI assistants that can help operators understand complex network behaviors and predict potential issues. By leveraging NRP's managed LLM service and GPU resources, students will create a Kubernetes-native system that scales across the distributed research network infrastructure, providing both real-time diagnostics and predictive analytics to improve network reliability and performance for researchers nationwide.

