---
title: "Drishti"
authors: [jeanlucabez, "Suren Byna"]
author_notes: ["Lawrence Berkeley National Laboratory", "The Ohio State University (OSU)"]
tags: ["osre26", "uc", "LBNL", "data science", "visualization", "profiling", "tracing"]
date: 2026-01-30T10:15:00-07:00
lastmod: 2026-01-30T10:15:00-07:00
---

[Drishti](https://github.com/hpc-io/drishti) is a novel interactive web-based analysis framework to visualize I/O traces, highlight bottlenecks, and help understand the I/O behavior of scientific applications. Drishti aims to fill the gap between the trace collection, analysis, and tuning phases. The framework contains an interactive I/O trace analysis component for end-users to visually inspect their applications' I/O behavior, focusing on areas of interest and getting a clear picture of common root causes of I/O performance bottlenecks. Based on the automatic detection of I/O performance bottlenecks, our framework maps numerous common and well-known bottlenecks and their solution recommendations that can be implemented by users.

### Drishti Comparisons and Heatmaps

The proposed work will include investigating and building a solution to allow comparing and finding differences between two I/O trace files (similar to a `diff`), covering the analysis and visualization components. It will also explore additional metrics and counters such as Darshan heatmaps in the analysis and visualization components of the framework.

- **Topics:** `I/O`, `HPC`, `data analysis`, `visualization`, `profiling`, `tracing`
- **Skills:** Python, data analysis, performance profiling
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** {{% mention jeanlucabez %}} and [Suren Byna](mailto:sbyna@lbl.gov)