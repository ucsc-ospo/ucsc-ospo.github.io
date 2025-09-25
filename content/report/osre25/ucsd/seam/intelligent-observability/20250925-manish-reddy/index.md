---
title: "Final Update: Building Intelligent Observability for NRP"
summary: "Completing OSRE 2025 with a novel InfoAgent architecture for ML-powered anomaly detection with trustworthy GenAI explanations for NRP monitoring."
authors:
  - kredd2506
tags: ["osre25", "final", "Observability", "GenAI"]
categories: ["osre25"]
date: 2025-09-25
lastmod: 2025-09-25
featured: false
draft: false
---
I'm excited to share the completion of my OSRE 2025 project, "*Intelligent Observability for NRP: A GenAI Approach*" and the significant learning journey it has been. We've successfully developed a novel InfoAgent architecture that delivers on our core goal: building an ML-powered service for NRP that analyzes monitoring data, detects anomalies, and provides trustworthy GenAI explanations.

## How Our Novel InfoAgent Architecture Advances the Observability Mission
Through extensive development and testing, I've learned tremendously about building production-ready AI systems and have implemented a novel InfoAgent architecture that orchestrates our specialized agents:

### 1. Prometheus Metrics Analysis Agent
- **Function**: Continuously ingests and processes NRP's Prometheus metrics
- **Progress**: Fully implemented data pipelines handling multiple metric types with optimized latency
- **Purpose**: Provides the foundation for anomaly detection by establishing normal behavior baselines

### 2. Query Refinement Agent (CROQ)
- **Function**: Clarifies ambiguous metrics or patterns before generating explanations
- **Progress**: Completed implementation of Conformal Revision of Questions for disambiguation
- **Purpose**: Ensures explanations address the right system behaviors (e.g., distinguishing CPU saturation from memory pressure)
- **Deliverable Impact**: Successfully improved accuracy of GenAI explanations by eliminating misinterpretations

### 3. Explanation Generation Agent (AIS)
- **Function**: Creates human-readable explanations and root-cause analysis
- **Progress**: Finalized the Automated Information Seeker with a complete Plan→Validate→Execute→Assess→Revise cycle
- **Purpose**: Transforms technical anomalies into actionable insights for operators
- **Deliverable Impact**: Delivers GenAI explanations with uncertainty quantification

## Completed Integration: The Novel InfoAgent Pipeline
We've successfully integrated all agents into a unified observability pipeline that represents our novel contribution:
1. **Data Collection**: Prometheus metrics → Analysis Agent (comprehensive metrics support)
2. **Anomaly Detection**: With statistical confidence bounds using conformal prediction
3. **Query Refinement**: Resolving ambiguities before explanation
4. **Explanation Generation**: Human-readable analysis with uncertainty awareness
5. **Feedback Loop**: System learning from operator interactions (implemented and tested)

## Hardware Testing Results
This project taught me valuable lessons about optimizing AI workloads on specialized hardware. We successfully tested our observability framework on Qualcomm Cloud AI 100 Ultra hardware:
- Achieved significant performance improvements over baseline CPU implementation
- Successfully ported and optimized GLM-4.5 for observability-specific tasks
- Validated that specialized AI hardware significantly enhances real-time anomaly detection

## Learning Journey and Novel Contributions
Throughout OSRE 2025, I've learned extensively about:
1. Building hierarchical agent coordination systems for complex reasoning
2. Implementing conformal prediction for trustworthy AI outputs
3. Creating self-correcting explanation pipelines
4. Developing adaptive learning systems from operator feedback

The novel InfoAgent architecture demonstrates promising results in our testing environment, with evaluation metrics and benchmarks still being refined as work in progress.

## Ongoing Work: Continuing Beyond OSRE
While OSRE 2025 is concluding, I'm actively continuing to contribute to this project:
1. Preparing the InfoAgent framework for open-source release with comprehensive documentation
2. Running extended evaluation tests on the Nautilus platform (work in progress)
3. Writing a research paper detailing our novel architecture
4. Creating tutorials to help others implement intelligent observability

**Project Updates and Code**: You can follow my ongoing contributions and access the latest code at [https://mreddy10.pages.nrp-nautilus.io/gsocnrp/](https://mreddy10.pages.nrp-nautilus.io/gsocnrp/)

## Acknowledgments
I'm deeply grateful to my lead mentor **Mohammad Firas Sada** for his exceptional guidance throughout this transformative learning experience. His insights have been invaluable in helping me develop the novel InfoAgent architecture and navigate the complexities of building production-ready AI systems.

The OSRE 2025 program has been an incredible journey of growth and discovery. I've learned not just how to build AI systems, but how to make them trustworthy, explainable, and genuinely useful for real-world operations. The novel InfoAgent architecture we've developed serves the original mission: creating an intelligent observability tool that helps NRP operators solve problems faster and keep complex research systems running smoothly.

I'm excited to continue contributing to this project and look forward to seeing how the community adopts and extends these ideas. Check out my contributions and ongoing updates at [https://mreddy10.pages.nrp-nautilus.io/gsocnrp/](https://mreddy10.pages.nrp-nautilus.io/gsocnrp/)!