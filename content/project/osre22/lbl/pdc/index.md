---
title: "Proactive Data Containers (PDC)"
authors: ["Suren Byna", "Houjun Tang"]
author_notes: ["Lawrence Berkeley Lab", "Lawrence Berkeley Lab"]
categories: ["osre22"]
tags: ["uc"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---
[Proactive Data Containers](https://sdm.lbl.gov/pdc/about.html) (PDC) are containers within a locus of storage (memory, NVRAM, disk, etc.) that store science data in an object-oriented manner.  Managing data as objects enables powerful optimization opportunities for data movement and
transformations, and storage mechanisms that take advantage of the deep storage hierarchy and enable automated performance tuning

### Python interface to an object-centric data management system

  * **Topics**: `Python`, `object-centric data management`, `PDC`
  * **Skills**: Python, C, PDC
  * **Difficulty**: Medium
  * **Size**: Large (350 hours)
  * **Mentor**: [Suren Byna](mailto:sbyna@lbl.gov), [Houjun Tang](mailto:htang4@lbl.gov)

[Proactive Data Containers (PDC)](https://sdm.lbl.gov/pdc/about.html) is an object-centric data management system for scientific data on high performance computing systems. It manages objects and their associated metadata within a locus of storage (memory, NVRAM, disk, etc.). Managing data as objects enables powerful optimization opportunities for data movement and transformations, and storage mechanisms that take advantage of the deep storage hierarchy and enable automated performance tuning. Currently PDC has a C interface. Providing a python interface would make it easier for more Python applications to utilize it.