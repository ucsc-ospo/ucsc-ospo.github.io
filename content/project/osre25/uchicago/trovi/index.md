---
title: "Chameleon Trovi Support for Complex Experiment Appliances"
authors: [keahey, mpowers]
author_notes: ["Chameleon Cloud, University of Chicago", "Chameleon Cloud, University of Chicago"]
tags: ["osre25", "reproducibility", "cloud computing", "systems architecture"]
date: 2025-02-18
lastmod: 2025-02-18
---

## Overview

The discoverability and accessibility of research artifacts remains a significant barrier to reproducibility in computer science research. While digital libraries index research papers, they rarely provide direct access to the artifacts needed to reproduce experiments, especially complex multi-node systems. Additionally, when artifacts are available, they often lack standardized metadata, versioning, and deployment mechanisms that would enable researchers to easily find and reuse them. This project addresses these challenges by extending Trovi, a repository of experimental artifacts executable on open platforms, to support complex, multi-node appliances, making sophisticated experimental environments discoverable, shareable, and deployable through a standardized interface - ultimately lowering the barriers to reproducing complex systems experiments.

[Chameleon](chameleoncloud.org/) has historically enabled researchers to orchestrate complex appliances—large, multi-node clusters configured via OpenStack Heat—to conduct advanced experiments. Meanwhile, Chameleon team introduced [Trovi](chameleoncloud.org/experiment/share) as repository for open platforms (beyond Chameleon) that pioneers mechanisms for artifact and platform integration leading to immediate execution for pratical reproducibility. This project aims to bridge the two by adding support in Trovi for importing, discovering, and launching complex appliances. By integrating these capabilities, researchers will be able to one-click deploy complex appliances directly from the Trovi dashboard, archive them for future reference, and reproduce experiments on demand.

## Key Outcomes

- Extended Trovi API: Enable the import and management of complex appliances as artifacts.
- Streamlined One-Click Launch: Integrate with Chameleon’s existing provisioning workflows so users can launch multi-node clusters directly from Trovi.
- Enhanced Dashboard Experience: Provide UI assistance for discovering, reviewing, and customizing complex appliance artifacts.
- Improved Artifact Reproducibility: Automate the process of exporting CC-snapshot images and other resources to ensure everything is preserved across sites (UC, TACC), highlighting any parameters that need user attention for cross-site portability.

**Topics**: `Reproducible Research`, `Cloud Computing & Orchestration`, `OpenStack Heat`, `UI/UX & Web Development`

**Skills**: Python, APIs, Cloud (OpenStack), DevOps & Automation, Frontend

**Difficulty**: Hard

**Size**: Large

**Mentors:** {{% mention mpowers %}}

**Tasks**:
  - Extensions to the Trovi API
    - Add support for importing complex appliances as artifacts (including Heat templates, metadata, and associated disk images).
    - Develop methods for tagging, versioning, and categorizing these appliances, making them easier to discover.
  - One-Click Launch of Complex Appliances
    - Integrate with Chameleon’s orchestration engine, enabling single-click cluster deployments from the Trovi UI.
    - Validate correct configuration and resource availability through automated checks.
  - Trovi Dashboard Enhancements
    - Update the front-end to provide intuitive controls for customizing or parameterizing complex appliances before launching.
    - Offer a clear workflow for reviewing dependencies, resource requirements, and usage instructions.
  - Automated Export & Multi-Site Testing
    - Streamline the export of snapshots or images into Trovi as part of the appliance import process.
    - Optionally re-run the imported appliances at multiple sites (UC, TACC), detecting any unparameterized settings or missing dependencies.
