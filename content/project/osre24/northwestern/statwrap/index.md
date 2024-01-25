---
title: "StatWrap"
authors: [lrasmus]
author_notes: ["Northwestern University"]
tags: ["osre24", reproducibility]
date: 2024-01-24
lastmod: 2024-01-24
---

[StatWrap](https://sites.northwestern.edu/statwrap/) is a free and open-source assistive, non-invasive discovery and inventory tool to document research projects. It inventories project assets (e.g., code files, data files, manuscripts, documentation) and organizes information without additional input from the user. It also provides structure for users to add searchable and filterable notes connected to files to help communicate metadata about intent and analysis steps.

At its core, StatWrap helps investigators identify and track changes in a research project as it evolves - which may affect reproducibility. For example: (1) people on the project can change over time, so processes may not be consistently executed due to transitions in employment; (2) data changes over time, due to accruing additional cases, adding new variables, or correcting mistakes in existing data; (3) software (e.g. used for data preparation and statistical analysis) evolves as it is edited, improved, and optimized; and (4) software can break or produce different results due to changes 'under the hood' such as updates to statistical packages, compilers, or interpreters. StatWrap passively and actively documents these changes to support reproducibility.

Additional information:

* [StatWrap home](https://sites.northwestern.edu/statwrap/)
* [StatWrap code (GitHub)](https://github.com/stattag/statwrap)

### Reproducibility Checklists

- **Topics**: `reproducibility`, `user interface`, `checklists`
- **Skills**: JavaScript, React
- **Difficulty**: Medium
- **Size**: Large (350 hours)
- **Mentor**: {{% mention lrasmus %}}

This goal of this project is to develop support within StatWrap to generate customizable reproducibility checklists. The developer will use the metadata and user input collected by StatWrap to automatically generate checklists. This functionality will allow investigators to automatically generate a document indicating what practices they've followed to support reproducibility. Part of the project will involve surveying proposed reproducibility checklists and considering what to implement in StatWrap. This work will take a systematic approach to documenting reproducibility, much like PRISMA checklists for systematic reviews or CONSORT checklists for clinical trials.

The specific tasks of the project include:

* Identify candidate reproducibility checklists to use as guides
* Create the data structure for configuring reproducibility checklists
* Display the reproducibility checklist in the user interface
* Store responses and comments to the checklist as provided by the user
* Generate a reproducibility checklist report from StatWrap


