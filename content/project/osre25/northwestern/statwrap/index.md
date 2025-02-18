---
title: "StatWrap"
authors: [lrasmus]
author_notes: ["Northwestern University"]
tags: ["osre25", "reproducibility"]
date: 2025-02-09
lastmod: 2025-02-09
---

[StatWrap](https://sites.northwestern.edu/statwrap/) is a free and open-source assistive, non-invasive discovery and inventory tool to document research projects. It inventories project assets (e.g., code files, data files, manuscripts, documentation) and organizes information without additional input from the user. It also provides structure for users to add searchable and filterable notes connected to files to help communicate metadata about intent and analysis steps.

At its core, StatWrap helps investigators identify and track changes in a research project as it evolves - which may affect reproducibility. For example: (1) people on the project can change over time, so processes may not be consistently executed due to transitions in employment; (2) data changes over time, due to accruing additional cases, adding new variables, or correcting mistakes in existing data; (3) software (e.g. used for data preparation and statistical analysis) evolves as it is edited, improved, and optimized; and (4) software can break or produce different results due to changes 'under the hood' such as updates to statistical packages, compilers, or interpreters. StatWrap passively and actively documents these changes to support reproducibility.

Additional information:

* [StatWrap home](https://sites.northwestern.edu/statwrap/)
* [StatWrap code (GitHub)](https://github.com/stattag/statwrap)

### Project Search

- **Topics**: `search`, `user interface`, `indexing`
- **Skills**: JavaScript, React
- **Difficulty**: Medium
- **Size**: Large (350 hours)
- **Mentor**: {{% mention lrasmus %}}, [Eric Whitley](mailto:ewhitley@northwestern.edu)

The goal of this project is to leverage the information entered by users and passively discovered by StatWrap to facilitate cross-project searching.  This functionality will allow investigators to search across projects (current and past) to find relevant projects, assets, and notes.  Given the potentially sensitive nature of data included in projects, the indexing of content for searching must be done locally.

The specific tasks of the project include:

* Identify and evaluate open-source projects to index content for searching
* Add a new classification for projects of “Active” and “Past” in the user interface
* Implement the search capability within the user interface
* Develop unit tests and conduct system testing



