# OSRE 2026 Final Report — CellQuery-ST (TileTalk)

**Cell-Aware Query Grounding for Single-Cell and Neighborhood Retrieval from Histology**

*Google Summer of Code 2026 · OSRE / UC OSPO / CROSS*
*Contributor: Tong Wu ([@twu0955](https://github.com/twu0955)) · Mentor: Xi Li*

- **Code (all GSoC work):** this repository — <https://github.com/twu0955/CellQuery-ST>
- **Final GSoC commit / tag:** `gsoc-2026-final` (work after this tag is post-GSoC)
- **My commits:** <https://github.com/twu0955/CellQuery-ST/commits/main>

*(The benchmark — queries, candidate pool, and labels — is regenerated
reproducibly from public Xenium data by the pipeline; see the README.)*

---

## 1. Project goals

Computational-pathology models can predict gene expression or answer broad,
slide-level questions, but they cannot answer **cell-aware** questions about an
H&E histology image — e.g. *"Where are the B cells?"*, *"Which regions look like
a vascular niche?"*, or *"Which cells express CD79A?"*.

**CellQuery-ST** set out to make this kind of biologically grounded querying
possible on new slides: learn from spatial-omics data at training time, but need
**only the H&E image at inference**. The framework I built is called **TileTalk**.
It frames the task as retrieval: given a natural-language query, rank the cells
(or their neighborhoods) in an H&E image by relevance.

## 2. What I did

- **An open benchmark, derived automatically — no manual annotation.**
  I turn paired 10x Xenium spatial omics into per-cell labels (marker-gene
  z-scoring for cell lineages; a *k*-NN composition graph for spatial niches) and
  release **34 natural-language queries** across four task families —
  **cell-type, cell-state, gene-marker, and spatial-niche grounding** — each with
  **seen / paraphrase / unseen-concept** splits and a full metric suite
  (Precision@K, Recall@K, mAP, MRR, nDCG@10, Enrichment@K). The marker-derived
  labels were validated against unsupervised Leiden clustering (0.87 agreement).
- **A reusable slide indexing & retrieval pipeline.**
  Each slide becomes a spatial index of cells, **multi-scale patches
  (~35 / 81 / 186 μm)**, and spatial neighbors; patches are embedded with
  **frozen pathology encoders (BiomedCLIP, PLIP, UNI2-h)**, fused per cell, and
  scored by a lightweight per-query head. Transcriptomic labels are training
  targets only; inference uses **H&E alone**, with 5-fold out-of-fold scoring to
  prevent leakage.
- **A full baseline suite & evaluation under one protocol.**
  Random floor; a **transcriptomic oracle** upper bound; **zero-shot
  pathology–language models** (BiomedCLIP / PLIP / CONCH); **two-stage
  predict-then-rank** baselines from the H&E→expression literature (ST-Net,
  BLEEP, and a ridge variant); and a linear probe — all evaluated for
  seen / paraphrase / unseen generalization.
- **Results.** TileTalk reaches **Enrich@10 = 4.95** — a **5.3× improvement over
  zero-shot** models (which stay near chance) — recovering much of the gap to the
  molecular oracle. It **generalizes across two tissues (breast + lung) and two
  gene panels**, holds up on an **external HEST cohort**, and supports
  **open-vocabulary text routing** for reworded and novel queries.
- **Reproducibility.** Fixed candidate pool, query set, and random seeds; an
  end-to-end `scripts/run_all.sh`; and scripts that regenerate every metric table.

## 3. Current state

The framework is **working and reproducible end-to-end**. From a raw Xenium
section, the pipeline preprocesses the slide, builds the query set and candidate
pool, extracts multi-scale patches, encodes them, trains the per-query heads, and
produces all retrieval metrics. All four benchmark task families, the full
baseline suite, cross-tissue / cross-panel validation, external HEST validation,
and open-vocabulary routing are implemented and evaluated. A one-command run
(`bash scripts/run_all.sh`) reproduces the core breast-cancer results from public
data.

## 4. What's left to do

- Add the **communication-hotspot grounding** task family (the fourth family in
  the original proposal) to complete the intended benchmark scope.
- Improve **label-free open-vocabulary querying** — the current bottleneck is
  text→concept routing (~53% top-1), not the image representation.
- Validate on **further HEST cohorts** for broader cross-platform transfer.
- Polish **documentation and tutorial notebooks** (preprocess a new slide → run
  queries → evaluate).
- Finalize the **packaged release** (pip install, hosted model/embeddings).

## 5. Code

This is a **new, single-purpose open-source repository** created for the project
(not a patch to an existing upstream project), so the **entire repository is the
contribution**. The `README.md` documents install, data download, and one-command
reproduction; the pipeline is designed to extend to new slides and new queries.

| Path | What it contains |
| --- | --- |
| `tiletalk/` | Core library — `data`, `patches`, `encoders`, `features`, `probe` (the per-query head), `queries`, `metrics`, `index` |
| `scripts/` | End-to-end pipeline — `preprocess_xenium`, `build_query_set`, `extract_cell_patches`, `build_cell_index`, `run_retrieval`, `run_twostage_baselines`, `evaluate_retrieval` |
| `configs/` | Dataset configs (breast Rep 1 / Rep 2, lung) |
| `scripts/run_all.sh` | One-command reproduction from public data |

> In the code, the **`cellseek`** baseline key is **TileTalk (ours)** — the
> per-query head over the fused frozen features.

## 6. Challenges & what I learned

- **No ground truth for cell-aware queries in H&E.** I learned to derive
  supervision automatically from paired spatial omics, then *validate* those
  labels against unsupervised structure rather than trusting them blindly.
- **Imperfect post-Xenium images.** ~1/3 of cells fall in torn/blank regions;
  restricting evaluation to tissue-bearing cells (performance essentially
  unchanged) taught me to rule out shortcut features before claiming a result.
- **Direct beats two-stage.** Predicting the transcriptome first and reading it
  back compounds error; learning relevance directly on the same features is both
  simpler and stronger.
- **Open-vocabulary is a *language* problem.** With a perfect concept router the
  visual heads nearly match per-query supervision, isolating text→concept routing
  as the real bottleneck — a clear direction for future work.

## 7. Acknowledgements

Huge thanks to my mentor **Xi Li** and the **OSRE / UC OSPO / CROSS** team for
their guidance throughout the summer. This was my first end-to-end open-source
research project — from an idea to a reproducible framework and open benchmark —
and an enormously rewarding experience.
