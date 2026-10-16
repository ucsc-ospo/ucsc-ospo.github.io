---
title: "NRPilot, a Kubernetes-Aware Assistant for NRP"
subtitle: "Delivering a deployed, documentation-grounded backend for safer cluster diagnostics"
summary: "A final reflection on building and deploying NRPilot: an open-source AI assistant that combines read-only Kubernetes diagnostics with official NRP documentation."
authors:
  - sod
tags: ["osre26", "gsoc", "ucsd", "nrp", "kubernetes", "llm", "ai", "backend", "open source"]
categories: ["GSoC 2026", "NETAI", "NRPilot", "Open Source"]
date: 2026-08-18
lastmod: 2026-08-18
featured: true
draft: false

image:
  caption: "NRPilot: AI-assisted Kubernetes diagnostics for the National Research Platform"
  focal_point: "Center"
  preview_only: false
---

This final update concludes my Google Summer of Code 2026 work with UC OSPO on [NRPilot](https://github.com/nrp-nautilus/nrpilot-api), an AI-powered assistant for the National Research Platform (NRP). In my [introductory post](/report/osre26/ucsd/netai/20260617-sod/), I described the goal of making complex platform and network operations easier to understand through natural language interaction. At [midterm](/report/osre26/ucsd/netai/20260727-sod/), the focus was on establishing a clean and safe backend foundation. Since then, that foundation has become a deployed, open-source service with a fuller set of diagnostics and documentation capabilities.

The deployed project is available at [NRPilot API documentation](https://nrpilot-api.nrp-nautilus.io/docs).

## What NRPilot Delivers

NRPilot is designed to help researchers and operators investigate NRP workloads without requiring them to begin with Kubernetes commands, dashboards, or documentation. A user can ask a question in plain language, and the agent can ground its response in the appropriate source: live, read-only Kubernetes information for operational questions and official NRP documentation for guidance questions.

The backend exposes a FastAPI chat API and health endpoints, while the agent layer orchestrates the available tools. I kept these responsibilities deliberately separate: API routes validate and return requests, application services coordinate domain behavior, adapters isolate external systems, and the LangChain-based agent and tools remain confined to the AI layer. This design makes the system easier to test and extend without letting Kubernetes or LLM specific concerns spread across the application.

## Expanding Read-Only Diagnostics

The initial diagnostics MVP supported inspecting namespaces, pods, deployments, pod details, events, and logs. The final phase expanded that set of read-only capabilities to cover the information commonly needed when investigating a workload problem:

- namespace and pod status
- pod and namespace events for scheduling, image-pull, and crash-loop signals
- pod logs and deployment state
- resource quotas and current resource usage
- node status

These tools call the Kubernetes service rather than interacting with the Kubernetes API directly. Keeping the tool layer thin was an important safety and maintainability decision: it lets the agent request evidence while the service and adapter layers own integration details and error handling. The assistant is intentionally limited to read-only operations, so it can assist investigation without changing user workloads.

## Grounding Answers in NRP Documentation

A useful operational assistant needs more than live cluster data. It also needs to explain how NRP services and policies are meant to be used. To support that, I added a documentation domain model, service, adapter, and agent tool that search the official NRP documentation and return source URLs with relevant excerpts.

In the final iteration, I improved retrieval quality by ranking page content and headings more highly than link text, and added time-to-live caching for discovered documentation links. These changes make repeated searches more efficient while improving the likelihood that the most relevant official guidance is surfaced. Just as importantly, the design keeps documentation evidence separate from cluster evidence, helping responses be clearer about what is currently happening and what the published guidance recommends.

## Engineering for Reliability

Building an AI feature for operations reinforced that the surrounding software engineering matters as much as the model. The project includes Docker packaging, Kubernetes deployment support, CI/CD validation and image publishing, typed Python models, structured logging, and a test suite that mocks external dependencies instead of requiring a live cluster.

This approach made it possible to test the Kubernetes client, service layer, tools, API behavior, agent configuration, and documentation retrieval independently. Structured logs capture tool invocation and retrieval lifecycle events without recording sensitive query contents, supporting observability while treating operational context carefully.

The main implementation milestones are available in the project's pull requests, including the initial backend and deployment setup, the Kubernetes adapter and service layers, the diagnostics chat MVP, documentation integration, expanded diagnostics, and documentation ranking and caching improvements. The full history is available in the [nrpilot-api pull requests](https://github.com/nrp-nautilus/nrpilot-api/pulls).

## Lessons and Looking Ahead

My biggest lesson from this project is that an operational AI assistant must be designed around trustworthy boundaries. The assistant should know when to consult Kubernetes and when to consult documentation. Read-only tools, explicit service boundaries, source-linked documentation, and thorough tests are all practical mechanisms for earning that trust.

The project also strengthened my experience with cloud-native backend development, dependency injection, AI orchestration, and designing software that can evolve safely. There is still room to extend NRPilot with conversation persistence, authentication, additional observability integrations, and a user interface. The backend delivered this summer provides a stable base for those next steps.

I am grateful to my mentors and the UC OSPO and NRP communities for their guidance throughout the summer. It has been rewarding to turn an early idea for an AI-powered NRP support assistant into a deployed service that can help make Kubernetes diagnostics and platform guidance more accessible.
