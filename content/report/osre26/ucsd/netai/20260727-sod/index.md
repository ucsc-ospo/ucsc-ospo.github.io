---
title: "Midterm Blog: Building the NRPilot Backend"
subtitle: "A foundation for Kubernetes-aware, documentation-grounded AI assistance"
summary: "A midterm reflection on building the NRPilot backend: the architecture, progress so far, challenges, and next steps."
authors:
  - sod
tags: ["osre26", "gsoc", "ucsd", "nrp", "kubernetes", "llm", "ai", "backend"]
categories: ["GSoC 2026", "NRPilot", "Open Source"]
date: 2026-07-27
lastmod: 2026-07-27
featured: true
draft: false

image:
  caption: "Building an AI assistant for the National Research Platform"
  focal_point: "Center"
  preview_only: false
---

Hello! This midterm update follows the [introductory blog](/report/osre26/ucsd/netai/20260617-sod/) and reflects the progress made so far on the NRPilot backend project under UC OSPO and Google Summer of Code 2026. The earlier post outlined the broader vision for an AI-powered assistant that helps researchers and students better understand and troubleshoot the National Research Platform (NRP); this update focuses on the work that has turned that vision into a working backend foundation.

The project is open source and lives on GitHub at [nrpilot-api](https://github.com/Segun-Ogundipe/nrpilot-api). At a high level, the goal is to make NRP operations more accessible. Instead of relying only on manual inspection of Kubernetes resources or documentation, the system should let users ask questions in plain English and receive grounded answers that are informed by both live cluster data and official NRP guidance.

## What I’ve Built So Far

The first half of the summer has been centered on establishing a solid foundation for the service.

One of the most important pieces was setting up a FastAPI-based application structure with clear API routes and a layered architecture. The backend now exposes a chat endpoint that can receive a user question and pass it to an agent layer designed for orchestration. I also implemented the initial health endpoints and request logging so the service is easier to run, observe, and debug.

A major part of the project is making the assistant useful in real operational contexts. To support that, I built a Kubernetes integration layer that can inspect namespaces, list pods, describe pod status, retrieve pod events, view logs, and list deployments. These capabilities are exposed through read-only tools that the agent can call when answering questions about cluster health or resource state.

I also wired in a documentation lookup capability so the assistant can answer questions about NRP guidance, services, and usage patterns using official documentation sources. One important design requirement here was to keep documentation answers distinct from live cluster evidence, so the system can clearly separate “what the docs say” from “what the cluster is currently doing.”

A number of pull requests have helped shape the project so far. Some of the key ones include:

- [PR #1:](https://github.com/nrp-nautilus/nrpilot-api/pull/1) initial backend setup with Docker support and health checks
- [PR #2:](https://github.com/nrp-nautilus/nrpilot-api/pull/2) CI/CD automation for validation, image publishing, and deployment
- [PR #3:](https://github.com/nrp-nautilus/nrpilot-api/pull/3) foundational Kubernetes integration and deployment support
- [PR #4:](https://github.com/nrp-nautilus/nrpilot-api/pull/4) Kubernetes adapter implementation
- [PR #5:](https://github.com/nrp-nautilus/nrpilot-api/pull/5) Kubernetes domain models and service layer
- [PR #6:](https://github.com/nrp-nautilus/nrpilot-api/pull/6) read-only Kubernetes diagnostics chat MVP
- [PR #8:](https://github.com/nrp-nautilus/nrpilot-api/pull/8) documentation domain model, service, and tool integration

You can follow the full list of PRs here: [nrpilot-api pull requests](https://github.com/nrp-nautilus/nrpilot-api/pulls).

## What I’ve Learned

This project has been especially valuable because it sits at the intersection of backend engineering, AI orchestration, and distributed systems. One of the biggest lessons so far has been the importance of designing the application around boundaries: making sure the API layer stay thin, the agent logic is isolated, and external integrations such as Kubernetes and documentation services are kept behind well-defined interfaces.

I’ve also become more deliberate about making the system safe and reliable. Since this assistant is meant to support operational workflows, it needs to be conservative in what it claims. This has shaped how I think about the tool design, especially when it comes to read-only operations, error handling, and making sure the agent does not overstate its confidence.

## Challenges and Adjustments

The biggest challenge has been balancing ambition with careful implementation. The project involves multiple moving pieces at once: an LLM agent, tool execution, Kubernetes integrations, documentation retrieval, and API design. Getting those pieces to work cohesively required more planning than I initially expected.

Another challenge has been ensuring that the assistant is grounded in the right source of truth. For cluster questions, the answer should come from Kubernetes data; for documentation questions, it should come from the NRP docs. That distinction is simple conceptually, but it has influenced a lot of the design decisions around how tools are structured and how the agent is prompted.

There have also been practical lessons around code organization and maintainability. As the project grows, it is increasingly important to avoid letting business logic leak into FastAPI routes or into the tool layer. Keeping the architecture clean has been a priority from the beginning, and that discipline is paying off as the system becomes more capable.

## What’s Next

For the second half of the summer, I plan to build on the current foundation by expanding the assistant’s capabilities. The next milestones include stronger conversational behavior, improved handling of more complex diagnostics, better persistence and authentication support, and the implementation of a user interface so the experience can become more accessible and interactive for researchers.

I’m also looking forward to making the agent more useful in real workflows by expanding the range of Kubernetes operations it can support and improving how it responds to ambiguous or incomplete questions. The goal is not just to get a working prototype, but to create a backend and interface that are reliable, extensible, and genuinely helpful to researchers using NRP.

Overall, this first half of the project has been a strong learning experience. I’m excited about the progress so far, and I’m looking forward to turning this early foundation into a more capable and polished assistant in the second half.

That’s all for now—stay tuned for the next update.
