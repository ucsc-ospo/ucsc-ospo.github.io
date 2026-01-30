---
title: "Midterm Update: Building Intelligent Observability for NRP"
summary: "Progress on developing ML-powered anomaly detection with trustworthy GenAI explanations for NRP monitoring."
authors:
  - kredd2506
tags: ["osre25", "midterm", "Observability", "GenAI"]
categories: ["Progress Updates"]
date: 2025-08-01
lastmod: 2025-08-01
featured: false
draft: false
---
I'm pleased to share the progress we've made on my OSRE 2025 project, "*Intelligent Observability for Seam: A GenAI Approach*" since my initial announcement. We're working toward our core goal: building an ML-powered service for NRP that analyzes monitoring data, detects anomalies, and provides trustworthy GenAI explanations.

## How Our Agents Support the Observability Mission
We've been developing specialized agents and tools that work together to support our original project vision:

### 1. Prometheus Metrics Analysis Agent
- **Function**: Continuously ingests and processes NRP's Prometheus metrics
- **Progress**: We've implemented initial data pipelines for key system metrics
- **Purpose**: Provides the foundation for anomaly detection by establishing normal behavior baselines

### 2. Query Refinement Agent (CROQ)
- **Function**: Clarifies ambiguous metrics or patterns before generating explanations
- **Progress**: We've implemented a basic version of Conformal Revision of Questions to resolve metric ambiguities
- **Purpose**: Aims to ensure explanations address the right system behaviors (e.g., distinguishing CPU saturation from memory pressure)
- **Deliverable Impact**: We hope this will improve accuracy of GenAI explanations by eliminating misinterpretations

### 3. Explanation Generation Agent (AIS)
- **Function**: Creates human-readable explanations and root-cause analysis
- **Progress**: We've built a prototype of the Automated Information Seeker with a Plan→Validate→Execute→Assess→Revise cycle
- **Purpose**: Transforms technical anomalies into actionable insights for operators
- **Deliverable Impact**: Intended to directly deliver on the GenAI explanation component of our tool

## Integration Progress
We're working to connect our agents into a unified observability pipeline:
1. **Data Collection**: Prometheus metrics → Analysis Agent
2. **Anomaly Detection**: With statistical confidence bounds (in development)
3. **Query Refinement**: Resolving ambiguities before explanation
4. **Explanation Generation**: Human-readable analysis with uncertainty awareness
5. **Feedback Loop**: System learning from operator interactions (planned)

## Hardware Testing Opportunity
This project has given us a valuable opportunity to test our observability framework on Qualcomm Cloud AI 100 Ultra hardware. We're beginning to port different LLM architectures specifically for:
- Exploring anomaly detection performance on specialized AI hardware
- Testing explanation generation quality across different model architectures
- Comparing GLM-4.5 against other models for observability-specific tasks

## Next Phase: Completing the Observability Tool
For the remainder of OSRE 2025, we're focused on:
1. Finalizing integration of all agents into a cohesive anomaly detection tool with matrix
2. Validating that our GenAI explanations help operators resolve issues faster for users, which we plan to test on the nautilus matrix platform
3. Optimizing performance on specialized hardware for NRP's scale
4. Preparing the open-source release of our intelligent observability tool

## Acknowledgments
I'm deeply grateful to my lead mentor **Mohammad Firas Sada** for his guidance in keeping our work focused on NRP's observability needs. His insights have been invaluable in navigating the challenges of this project.

While we've developed several agents and frameworks, everything we're building serves the original mission: creating an intelligent observability tool that helps NRP operators solve problems faster and keep complex research systems running smoothly.

I look forward to sharing more progress on our observability tool with GenAI explanations in the coming weeks!