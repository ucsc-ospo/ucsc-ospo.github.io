---
title: "Contextualization – Extending Chameleon’s Orchestration for One-Click Experiment Deployment" 
authors: [mpowers, msherman]
author_notes: ["University of Chicago", "University of Chicago"]
tags: ["osre25", "reproducibility", "cloud computing", "systems architecture"]
date: 2025-02-18
lastmod: 2025-02-18
---

## Overview

[Chameleon](chameleoncloud.org) already provides powerful capabilities to orchestrate and configure resources through Heat templates (similar to Terraform) and the [python-chi](https://python-chi.readthedocs.io/) library. However, these focus primarily on provisioning (i.e., allocating and configuring hardware resources). This project goes a step further by addressing contextualization—the process of creating complete, ready-to-use experimental environments that incorporate everything from network layout to instance-level configuration and discovery—with additional features such as parameterized templates, experiment-level metadata, and output reporting.

## Key Outcomes

- Template-Based One-Click Launch: Users can deploy multi-resource experiments (VMs, networks, storage, etc.) via a single click or a minimal set of input parameters.
- Enhanced Experiment Contextualization: Each launched resource can gain access to global “experiment-level” metadata (e.g., IP-to-hostname mappings for cluster authentication) and outputs that summarize important details.
- Streamlined User Experience: An asynchronous deployment workflow that provides notifications and uses “outputs” to highlight critical connection information (e.g., bastion host IP, final results).
- Optional Advanced Features: Partial reconfiguration to avoid full rebuilds when changes are minor, an “export” function to capture existing deployments into a new template, and potential publishing to Trovi for reproducibility and archiving.

**Topics**: Cloud Computing & Orchestration, Infrastructure as Code, DevOps & Automation, Reproducible Research Environments
**Skills**:
- OpenStack & Heat Templates: Familiarity with provisioning resources on Chameleon using Heat or Terraform-like workflows.
- Python & Scripting: For enhancing or extending the python-chi library.
- Systems / Network Knowledge: Understanding multi-VM topologies, cluster configurations, and network-level interactions.
- CI/CD & DevOps: Experience building or integrating asynchronous deployment and notifications.
**Difficulty**: Hard
**Size**: Large (suitable for a semester-long project or a summer internship)
**Mentors**: {{% mention msherman %}}, {{% mention mpowers %}}
**Tasks**:
- One-Click Template Launch
  - Design a template (in Heat or similar) specifying multiple cloud resources (images, networks, disk images, SSH keys, etc.).
  - Ensure the template author can define input parameters with defaults.
  - Allow the user to launch the template quickly with default values or adjust parameters before deployment.
- Asynchronous Provisioning & Notifications
  - Implement a long-running process that deploys resources step-by-step.
  - Provide status updates to the user (e.g., via UI notifications, email, or logs) when deployments complete or fail.
- Experiment-Level Metadata
  - Inject metadata such as IP-to-hostname mappings to each instance for easy cluster authentication.
  - Allow the template to define “outputs” (like a public IP of a bastion or location of final results).
- Partial Reconfiguration (Optional)
  - Enable partial updates if only one of several servers changes, saving time and resources.
  - Improve fault tolerance by avoiding full redeploys in the event of partial failures.
- Export Running Configurations into a New Template (Optional)
  - Build a web-interface or script to detect existing user-owned resources (servers, networks, etc.).
  - Generate a proposed template from those resources, suggesting parameters (e.g., flavor, disk image, or SSH key).
  - Extend or modify existing templates by adding discovered resources.
- Integration with Trovi / Multi-Site Testing (Optional)
  - Provide a method to archive or publish the final template (and associated disk images, data sets) in Trovi.
  - Attempt to re-run the template at multiple Chameleon sites (e.g., UC, TACC) to identify parameters or modifications needed for cross-site reproducibility.