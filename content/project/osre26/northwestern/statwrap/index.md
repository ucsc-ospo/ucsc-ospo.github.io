---
title: "StatWrap"
authors: [lrasmus]
author_notes: ["Northwestern University"]
tags: ["osre26", "reproducibility"]
date: 2026-01-29
lastmod: 2026-01-29
---

[StatWrap](https://sites.northwestern.edu/statwrap/) is a free and open-source assistive, non-invasive discovery and inventory tool to document research projects. It inventories project assets (e.g., code files, data files, manuscripts, documentation) and organizes information without additional input from the user. It also provides structure for users to add searchable and filterable notes connected to files to help communicate metadata about intent and analysis steps.

At its core, StatWrap helps investigators identify and track changes in a research project as it evolves - which may affect reproducibility. For example: (1) people on the project can change over time, so processes may not be consistently executed due to transitions in employment; (2) data changes over time, due to accruing additional cases, adding new variables, or correcting mistakes in existing data; (3) software (e.g. used for data preparation and statistical analysis) evolves as it is edited, improved, and optimized; and (4) software can break or produce different results due to changes 'under the hood' such as updates to statistical packages, compilers, or interpreters. StatWrap passively and actively documents these changes to support reproducibility.

Additional information:

* [StatWrap home](https://sites.northwestern.edu/statwrap/)
* [StatWrap code (GitHub)](https://github.com/stattag/statwrap)

### Group and Individual Customizations

- **Topics**: `configuration`, `user interface`
- **Skills**: JavaScript, React
- **Difficulty**: Medium
- **Size**: Large (350 hours)
- **Mentor**: {{% mention lrasmus %}}, [Eric Whitley](mailto:ewhitley@northwestern.edu)

The goal of this project is to expand the existing capabilities of StatWrap to provide more flexibility to individual users and groups. Currently, features within StatWrap such as the directory template for creating new projects and the reproducibility checklist are static, meaning everyone who downloads StatWrap has the same configuration. However, each user and team work differently and should be able to configure StatWrap to support their needs.

When a user creates a new project, StatWrap provides a collection of project templates. These create a directory hierarchy, along with some seed files (e.g., a README.md file in the project root).  Different groups have their own conventions for creating project directories. While StatWrap can be released with additional project templates defined, there are many situations in which users would want to keep their project template local.  StatWrap should allow a user to create a project template configuration, from scratch or being seeded by the contents of an existing project.  A user should then be able to export this configuration, share it with others, and other user should have the ability to import the configuration into their instance of StatWrap.

Similarly, StatWrap provides a reproducibility checklist that includes six existing checklist items.  However, individual users and groups may have their own checklists, including institution-specific steps.  Similar to the project template, a user should be able to configure additional items for the checklist.  A user should be able to create a "checklist template" that can be used and applied in multiple projects.  A specific project's template should also be modifiable once the checklist has been created.

The specific tasks of the project include:

* Developing a configuration scheme for New Project templates
* Provide a way for a user to import/export a template for New Projects
* Develop a configuration scheme for Reproducibility Checklist questions
* Provide a way for a user to import/export a template for the Reproducibility Checklist
* Develop a configuration scheme for asset (file) attributes
* Develop unit tests and conduct system testing



