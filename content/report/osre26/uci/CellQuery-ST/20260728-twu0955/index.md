---
title: "Halfway Through OSRE 2026: Progress on CellQuery-ST"
subtitle: "CellQuery-ST: Cell-Aware Query Grounding for Single-Cell and Neighborhood Retrieval from Histology"
summary: "A mid-term update on building CellQuery-ST — a framework (which we call TileTalk) that answers natural-language, cell-aware questions about H&E histology images using spatial-omics supervision, with an open benchmark and reproducible baselines."
authors:
  - twu0955
tags:
  - osre26
categories: []
date: 2026-07-28
lastmod: 2026-07-28
featured: false
draft: false
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hi everyone! This is a mid-term update on **CellQuery-ST**, my OSRE 2026 project under the mentorship of **Xi Li**. The goal is to make *cell-aware* querying of histology images possible — answering questions like *"Where are the B cells?"*, *"Which regions look like a vascular niche?"*, or *"Which cells express CD79A?"* directly from an H&E image, using spatial-omics data only as supervision at training time. Over the first half I've turned this idea into a working framework (which we call **TileTalk**), an open benchmark, and a full set of baselines.

## 🚀 Achievements

### ✅ Built the benchmark from paired spatial omics — no manual annotation
I turn paired 10x Xenium spatial omics into **per-cell labels automatically**: marker-gene z-scoring assigns cell lineages (B cell, T cell, myeloid, endothelial, fibroblast, epithelial, mast), and a *k*-nearest-neighbor composition graph derives spatial niches. On top of these I released **34 natural-language queries** across four task families — **cell-type, cell-state, gene-marker, and spatial-niche grounding** — each with **seen / paraphrase / unseen-concept** splits and a full metric suite (Precision@K, Recall@K, mAP, MRR, nDCG@10, and label Enrichment@K). I validated that the marker-derived labels are real transcriptomic populations (0.87 agreement with unsupervised Leiden clustering).

### ✅ Built the slide indexing & retrieval pipeline
Each slide is preprocessed into a spatial index of cells, **multi-scale patches (~35 / 81 / 186 μm)**, and spatial neighbors. Patches are encoded with **frozen pathology encoders (BiomedCLIP, PLIP, UNI2-h)** and fused per cell, and a lightweight per-query head ranks the whole candidate pool by relevance. Crucially, the transcriptomic labels are used **only as training targets** — at inference the system needs **the H&E image alone**.

### ✅ Reproducible baselines & evaluation, from zero-shot to a molecular oracle
I implemented the full comparison spectrum under one protocol: a random floor, a **transcriptomic oracle** upper bound, **zero-shot pathology–language models** (BiomedCLIP / PLIP / CONCH), **two-stage predict-then-rank** baselines from the H&E→expression literature (ST-Net, BLEEP, and a ridge variant), and a linear probe — all scored with 5-fold out-of-fold estimation to prevent leakage, and evaluated for **seen / paraphrase / unseen** generalization.

### ✅ Results: recovering biological signal from H&E alone
TileTalk reaches **Enrich@10 = 4.95** (its top-ranked cells are ~5× more likely to be relevant than chance) — a **5.3× improvement over zero-shot** pathology–language models, which stay near chance. It **generalizes across two tissues (breast + lung) and two gene panels**, holds up on an **external HEST cohort** from a different lab, and supports **open-vocabulary text routing** for reworded and novel queries. We've written the work up as a manuscript, currently under review.

## 🧠 Challenges

- **No ground truth for cell-aware queries in H&E.** H&E carries no molecular labels, so I derive supervision from the paired spatial omics (marker z-scoring, niche composition) — no manual annotation, but it required careful label validation.
- **Imperfect post-Xenium images.** The H&E is stained after destructive Xenium cycles, so ~1/3 of cells fall in torn/blank regions. Restricting evaluation to tissue-bearing cells left performance essentially unchanged, confirming the signal comes from morphology, not blank-patch shortcuts.
- **Predicting expression first is the hard path.** Two-stage "predict genes, then answer" baselines compound error and underperform learning relevance directly — a finding that shaped the final design.
- **Open-vocabulary is a language problem.** With a perfect concept router the visual heads nearly match per-query supervision, so the bottleneck is text→concept routing (~53% top-1), not the image representation.

## 🔜 What's Next

- 🧬 Add the **communication-hotspot grounding** task family to complete the four-family benchmark.
- 🌐 Improve **label-free open-vocabulary querying** (better text→concept routing / image–text adapters).
- 🔁 Validate on **further HEST cohorts** for cross-platform transfer.
- 📓 Write **documentation and tutorial notebooks** (preprocess a new slide → run queries → evaluate).
- 📦 Prepare the **public open-source release**: code, query set, candidate pool, and precomputed embeddings.

## 🧾 Deliverables Progress

| Deliverable | Status |
| --- | --- |
| Benchmark — cell-type / cell-state / gene-marker / niche grounding | ✅ Completed |
| Benchmark — communication-hotspot grounding | 🟡 Planned |
| Slide indexing & retrieval pipeline | ✅ Completed |
| Reproducible baselines & seen/unseen evaluation | ✅ Completed |
| Cross-tissue, cross-panel & external (HEST) validation | ✅ Completed |
| Documentation & tutorial notebooks | 🟡 In Progress |
| Public open-source release (code, queries, pool, embeddings) | 🟡 In Progress |

## 🙌 Closing Thoughts

The first half has been incredibly rewarding — I went from an idea about "asking a histology image biological questions" to a working, reproducible framework with an open benchmark and a full baseline suite, and even a manuscript. Huge thanks to my mentor **Xi Li** and the OSRE / UC OSPO team for the guidance and support. In the second half I'll focus on the remaining task family, open-vocabulary querying, documentation, and a clean public release. If you work on computational pathology or spatial omics and want to chat, please reach out — thanks for following along!
