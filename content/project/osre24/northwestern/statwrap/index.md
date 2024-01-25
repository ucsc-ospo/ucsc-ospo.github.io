---
title: "StatWrap"
authors: [lrasmus]
author_notes: ["Northwestern University"]
tags: ["osre24", reproducibility]
date: 2024-01-24
lastmod: 2024-01-24
---

[StatWrap] (https://sites.northwestern.edu/statwrap/) is designed as a free and open-source assistive, non-invasive discovery and inventory tool to document research projects. It inventories project assets (e.g., code files, data files, manuscripts, documentation) and organizes information without additional input from the user, while also allowing users to add searchable and filterable notes connected to files to help communicate metadata about intent and analysis steps.

At its core, StatWrap helps you identify, track, and reflect on variation in your research project that could impact the ability to reproduce your work. Variation can happen in many places: (1) people on the project can change over time, so processes may not be consistently executed due to transitions in employment; (2) data changes over time, due to accruing additional cases, adding new variables, or correcting mistakes in existing data; (3) software (e.g. used for data preparation and statistical analysis) evolves as it is edited, improved, and optimized; and (4) software can break or produce different results due to changes ‘under the hood’ such as updates to statistical packages, compilers, or interpreters.

Additional information:

* [StatWrap home](https://sites.northwestern.edu/statwrap/)
* [StatWrap code (GitHub)](https://github.com/stattag/statwrap)

### Reproducibility Checklists

- **Topics**: `reproducibility`, `user interface`, `checklists`
- **Skills**: JavaScript, React
- **Difficulty**: Medium
- **Size**: Large (350 hours)
- **Mentor**: {{% mention lrasmus %}}

The metadata and user input collected by StatWrap can be used to support reproducibility 'checklists' to ensure that recommended practices for reproducible research are followed.  Although there is no definitive reproducibility checklist currently available (like PRISMA for systematic reviews), checklists in various forms do exist.

This project will develop support within StatWrap for supporting customizable reproducibility checklists.

The specific tasks of the project include:

* Identify candidate reproducibility checklists to use as guides
* Create the data structure for configuring reproducibility checklists
* Display the reproducibility checklist in the user interface
* Store responses and comments to the checklist as provided by the user
* Generate a reproducibility checklist report from StatWrap


