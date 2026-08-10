---
title: "Extending AIDRIN for Scientific Data Formats"
summary: "Extending AIDRIN with hardened HDF5 support and native Zarr and ROOT readers under mentorship from LBNL researchers as part of OSRE 2026."
authors: 
- dhanush010
- jeanlucabez
- surenbyna
tags: [
  "AIDRIN",
  "osre26"
]

categories: []

date: 2026-06-19
lastmod: 2026-06-19
featured: false
draft: false

# Featured image
image:
  caption: "AIDRIN - inspecting dataset readiness for AI pipelines"
  focal_point: Top
  preview_only: false
---

⏱️ Reading time: 2–3 minutes

Hi 👋

I'm Dhanush, a first-year Master's student in Computer Engineering at New York University. I like building systems that work reliably at scale, and I care a lot about data quality because I've seen firsthand what happens when you ignore it. Before NYU, I spent a year at Tata Consultancy Services building backend systems and monitoring production workflows, which gave me a very concrete sense of how data quality problems compound quietly until they suddenly aren't quiet anymore.

This summer I'm contributing to [AIDRIN](/project/osre26/lbl/aidrin) (AI Data Readiness Inspector) as part of OSRE 2026, under the mentorship of Dr. Jean Luca Bez and Prof. Suren Byna from the [Scientific Data Division](https://scidata.lbl.gov) at Lawrence Berkeley National Laboratory (LBNL).

[AIDRIN](https://github.com/idtlab/AIDRIN) is an open-source framework that helps researchers and data scientists evaluate whether a dataset is genuinely ready for AI workflows by assessing data quality,  FAIR-principle compliance, data structure performance, bias, and impact of data on AI applications. The idea is straightforward: before you trust a model, you should be able to trust the data behind it. AIDRIN also supports remediating data when lapses occur in the data used by AI applications.

## Why this work matters to me

While working on a course project building a taxi-trip prediction system, I spent an afternoon chasing a degraded prediction. The root cause was a single bad record propagating through the whole batch of data. I had to diagnose it manually. That experience stuck with me, because it showed me that data problems don't announce themselves. They just quietly make everything worse.

AIDRIN is built to surface those problems earlier. What drew me to this project is a gap that limits who can use it today: AIDRIN supports CSV, Excel, JSON, NumPy, and HDF5, but many scientific workflows rely on formats that are harder to flatten into a spreadsheet, such as ROOT in high-energy physics, Zarr in climate and genomics, and HDF5 layouts that aren't simple tables. Getting data out of those formats into CSV is often painful or lossy.

## What I'm working on this summer

My project is about improving AIDRIN’s support for data and file formats that are not tabular. I'll start by hardening the HDF5 reader, building an inventory of what's actually in each file, and handling real scientific layouts instead of assuming everything is a flat table. On top of that, I'm adding native support for Zarr and ROOT, two formats that show up constantly in climate, genomics, and high-energy physics workflows but aren't well served by converting everything to CSV first. I'm also building a pluggable ingestion layer for custom sources and multi-file support, so related datasets can be combined before analysis.

## What's next

Right now, I'm mapping how data flows from upload through to the metric modules and writing an HDF5 audit of sample files before changing implementation.

More updates as the summer goes on. If you work in data quality, scientific data management, or open-source tooling, I'd love to connect.

👉 [Read my proposal here](https://drive.google.com/file/d/1g44iFr41vXxzA6rlCRQ_1L-hkEqhS_Zu/view?usp=sharing)