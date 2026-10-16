---
title: "AIDRIN Midterm: HDF5 Inventory, Dataset Picker, and Zarr"
summary: "Halfway through GSoC/OSRE 2026: hardening AIDRIN’s HDF5 reader with inventory and dataset picking, plus Parquet and Zarr support, under mentorship from LBNL researchers."
authors:
- dhanush010
- jeanlucabez
- surenbyna
tags: [
  "AIDRIN",
  "osre26"
]

categories: []

date: 2026-07-27
lastmod: 2026-07-27
featured: false
draft: false

# Featured image
image:
  caption: "AIDRIN - inspecting dataset readiness for AI pipelines"
  focal_point: Top
  preview_only: false
---

⏱️ Reading time: 3–4 minutes

Hi again,

We're halfway through GSoC and I wanted to share what the past few weeks have actually looked like, what I built, what surprised me, and what's coming next.

## Where I've been spending my time

My project is about extending [AIDRIN](https://aidrin.readthedocs.io/en/latest/)(AI Data Readiness Infrastructure) to support the file formats that scientific researchers actually use. Before I could build anything new, though, I had to understand what was already there and where it was quietly breaking.

The HDF5 reader turned out to be more interesting than I expected. On the surface, it worked, files opened, metrics ran, numbers appeared. But when I started auditing it carefully, I found a few real problems. Some scientific HDF5 files were crashing with an undefined fill value error that wasn't being caught. Others were opening without errors but producing a single anonymous column of mashed-together data from unrelated arrays with completeness score of 1.0, everything looked fine, but the metrics were running on something that didn't represent the file at all. That second case is the scarier one because it fails silently.

Fixing this properly meant rethinking how the reader approaches hierarchical files. Instead of trying to flatten everything into one table or dataframe immediately, the reader now inventories the file first. Concretely, that means walking every dataset in the file and recording its path, shape, dtype, and size. From that list it classifies the layout: a single dataset can be read straight into a dataframe; several same length 1D arrays can be joined as columns; but mismatched root level lengths or hierarchical groups with mixed lengths (for example station waveforms under paths like S_01_01/X) are marked as needing selection. In those cases read() refuses to auto-flatten, and the UI shows a dataset picker so the user explicitly chooses what to analyse. The goal is simple: what the user selects should be exactly what the metrics analyse. No silent wrong reads.

That work landed in [#118](https://github.com/idtlab/AIDRIN/pull/118) (inventory + picker + fill-value handling), with follow-ups in [#169](https://github.com/idtlab/AIDRIN/pull/169).

## New format support

Parquet support landed earlier in the program. I've also been building a Zarr reader([#164](https://github.com/idtlab/AIDRIN/pull/164)), which follows the same inventory first approach, a Zarr store can contain many arrays with different shapes and meanings, so the same dataset picker pattern applies. The shared inventory / selection plumbing is meant to be reused by the ROOT reader next, so ROOT can plug into the same “list → classify → pick → load” flow instead of us rewriting that logic again.

Along the way, I also fixed some smaller things - Windows Celery documentation([#110](https://github.com/idtlab/AIDRIN/pull/110)), a bug where clearing a session while the server was still processing caused problems([#116](https://github.com/idtlab/AIDRIN/pull/116)), and a few correctness issues. These aren't the exciting parts of the project, but they're the kind of thing that makes a codebase more robust and nicer to work in and contribute to.

## What's next

The second half of the summer is about finishing what's started. Polish the Zarr reader, build the ROOT reader with TTree selection, unify error handling across all formats so failures surface consistently, and land the first version of the custom data ingestion interface that lets users bring in data from other file formats, databases, or APIs without having to modify AIDRIN's core code.

More updates soon. If you're working on data quality or scientific data tooling, I'd love to connect.
