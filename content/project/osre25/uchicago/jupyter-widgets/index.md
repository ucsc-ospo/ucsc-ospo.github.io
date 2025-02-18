---
title: "Widgets for Python-chi in Jupyter" 
authors: [mpowers, msherman]
author_notes: ["University of Chicago", "University of Chicago"]
tags: ["osre24", "reproducibility", "visualization", "UX"]
date: 2025-02-18
lastmod: 2025-02-18
---

## Overview

As cloud researchers often work with Jupyter Notebooks for interactive data analysis and experimentation, the [python-chi](https://python-chi.readthedocs.io/) library offers a powerful way to automate and control resources on [Chameleon Cloud](chameleoncloud.org). This project will extend python-chi by adding interactive widgets specifically designed for use in Jupyter, empowering users to launch, monitor, and manage their experiments without leaving the notebook environment. By bringing visual and intuitive controls directly into the user’s workflow, we aim to improve both reproducibility and usability for complex resource management tasks.

## Key Outcomes

- User-Friendly Jupyter Widgets: Develop a suite of widgets to visualize reserved resources, hardware availability, and experiment topologies in real time.
- Integrated Experiment Management: Enable researchers to orchestrate experiments (launch, configure, monitor) within a single, notebook-centric workflow.
- Enhanced Feedback & Usability: Provide clear, asynchronous status updates and resource reconfiguration progress, reducing confusion and user error.
- Improved Reproducibility: By automating and logging widget interactions, experiments become more traceable and easier to replicate.

**Topics**: Interactive Data Tools, Cloud Resource Management, DevOps & Automation, User Experience (UX)
**Skills**:
- Python & Jupyter: Experience creating custom Jupyter widgets, using ipywidgets or similar frameworks.
- Cloud Automation: Familiarity with how resources are provisioned, monitored, and deprovisioned on Chameleon.
- Frontend / GUI Development: Basic understanding of web technologies (HTML/CSS/JavaScript) can be helpful for widget design.
- Software Engineering & CI: Ability to version-control, test, and deploy Python packages.
**Difficulty**: Moderate
**Size**: Medium
**Mentor**: {{% mention msherman %}} {{% mention mpowers %}}
**Tasks**:
- Resource Visualization Widgets
    - Build custom widgets that show reserved resources (nodes, networks, storage) in Jupyter.
    - Provide an interactive topology view for experiments, indicating node statuses and connections.
- Experiment Setup & Execution
    - Add controls for launching and managing experiments directly from notebooks.
    - Show feedback (e.g., progress bars, status messages) as resources are being allocated or reconfigured.
- Hardware Availability & Status Tracking
    - Implement a widget that provides real-time data on Chameleon’s hardware availability (bare metal, VMs, GPU nodes, etc.).
    - Allow users to filter or select specific resources based on current hardware states.
- Usability & Feedback Loop
    - Gather user feedback on the widget designs and workflows.
    - Refine the interface to minimize clicks, improve clarity, and reduce friction for common tasks.
