---
title: "Halfway Through OSRE'26: CauST Meets Real Tissue"
subtitle: "A midterm update — from a synthetic proof of concept to a held-out-donor benchmark on human cortex"
summary: "Midterm update for my OSRE'26 project with UC Santa Cruz OSPO: CauST now runs end-to-end on real spatialLIBD DLPFC data, where 25 causally-selected genes beat the HVG baseline — and the full 2,000-gene pool — on a donor the selection never saw."
authors:
  - jiawei-li
tags: ["osre26", "gsoc", "caust", "spatial-transcriptomics", "causal-inference"]
categories: ["GSoC 2026", "CauST"]
date: 2026-08-13
lastmod: 2026-08-13
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Cortical layers on the held-out donor (slice 151673): manual annotation vs. the HVG baseline vs. CauST-selected genes."
  focal_point: "Center"
  preview_only: false
---

Hi again! It's been almost two months since my
[intro post](/report/osre26/uci/caust/20260618-jiawei-li/) about
[CauST](/project/osre26/uci/caust/), my OSRE'26 project with **UC Santa Cruz
OSPO** under the mentorship of {{% mention lijinghua %}}. As laid out in my
[proposal](https://summerofcode.withgoogle.com/media/user/af71a455291d/proposal/gAAAAABqM_mFg7Tevk5gpESIoYTWQJEwp7ino2Sk1bL27ndGikmQyZzxHMXUir1n4mz7qNhu3UZpMPdclfY6baYaL_wWfsTcesvczmVeH0MfaEGJKFz2TMc=.pdf),
CauST asks a causal question about spatial transcriptomics: which genes *cause*
a spot to belong to a spatial domain, rather than merely being *associated*
with it through some confounder? The halfway mark is a good time to take stock — the short version
is that the idea now survives contact with real tissue, and the code is public:
[github.com/land-saas/CauSt](https://github.com/land-saas/CauSt).

## 🚀 Achievements

### ✅ An end-to-end pipeline: knockout → invariance → selection

The core loop is implemented and tested. CauST trains a frozen spatial backbone
per tissue slice, silences each gene *in silico*, and measures how much the
embedding shifts. Genes are then scored by **mean effect minus λ times the
cross-slice standard deviation** — rewarding genes whose effect is large *and
stable across donors*. On a synthetic multi-donor cohort built to embarrass
variance-based selection, CauST recovers **8/8** planted causal genes where the
highly-variable-genes (HVG) baseline finds **1/8**, and clustering on the
selected genes hits ARI **1.000** on a held-out donor vs. **0.537 ± 0.133** for
HVG at the same gene budget.

### ✅ The same claim on real tissue

The synthetic trap is engineered, so the honest question was whether the story
survives real data. CauST now loads the **spatialLIBD human DLPFC** cohort —
10x Visium slices of dorsolateral prefrontal cortex with manual cortical-layer
annotations, the standard benchmark for spatial domain identification. The
setup mirrors the causal claim: genes are selected using two donors (two slices
each), and the third donor is evaluated **exactly once**, after all tuning.

On that never-seen donor, **25 CauST-selected genes reach ARI 0.459 ± 0.069**,
beating both the HVG baseline at the same budget (**0.351 ± 0.034**) and the
full 2,000-gene candidate pool (**0.378 ± 0.026**). Selecting 1.25% of the
candidate genes *improves* generalization to a new donor — exactly the
robustness CauST was designed for. The selected set is biologically legible,
too: it includes **MBP** (myelin / white matter), **CLU** and **SPARCL1**
(astrocytic genes with laminar expression), and **NRGN** (neurogranin),
alongside metabolic and ribosomal genes whose laminar gradients happen to be
donor-stable.

![Spatial domains on the held-out DLPFC donor](featured.png)
*The held-out donor: manual layer annotation (left), domains recovered from the
top-25 HVG genes (middle, ARI 0.351), and from the top-25 CauST genes (right,
ARI 0.459). The CauST set restores the layered banding that variance-based
selection smears.*

### ✅ Reproducibility as a feature, not an afterthought

Every experiment is config-driven and writes a content-addressed results
directory with the resolved config, metrics, and a provenance manifest (git
commit, package versions, seed, BLAS thread counts, artifact checksums).
`caust verify` re-runs any recorded run and fails if a number moved; CI proves
two separate processes produce **byte-identical artifacts** on every push. The
project moved to a [uv](https://docs.astral.sh/uv/)-managed environment — one
committed lockfile backs local dev, CI, and a hermetic Docker image — and the
DLPFC downloads are pinned to SHA-256 checksums, so the inputs of a run are as
fixed as its code. The test suite now sits at 98 tests with ~94% coverage.

### ✅ Making 2,000 knockouts cost seconds

Scoring a knockout per gene naively means a full forward pass per gene. Because
the reference backbone is linear after standardization, silencing one gene
shifts the embedding by a smoothed **rank-1 update** — O(N·d) per gene instead
of O(N·G·d). Scoring the full 2,000-gene candidate pool across five slices
takes seconds on a laptop, which is what makes the real-data benchmark (and a
[five-minute demo](https://github.com/land-saas/CauSt/blob/main/docs/demo.md)
of the whole project) practical.

## 🧠 Challenges

- **The first real-data attempt lost.** With the settings carried over from the
  synthetic benchmark (λ=2, a 50-gene budget), CauST scored *below* HVG on the
  held-out donor. The fix was methodological, not
  cosmetic: sweep λ and the gene budget **on the training donors only**, and
  use two slices per training donor so the cross-slice variance in the score is
  estimated from four slices rather than two. The held-out donor stayed
  untouched until a single final run.
- **Real data is messier than any simulation.** R-exported annotation files
  with shifted headers, duplicate gene symbols, one donor annotated with five
  layers instead of seven — each needed an explicit, tested decision in the
  loader rather than a silent workaround.
- **Honesty about markers.** Only one of the eight canonical layer markers in
  the candidate pool makes CauST's top-25 (HVG keeps two). CauST optimizes
  cross-donor predictive stability, not agreement with a curated panel — so the
  pipeline now reports marker recovery alongside ARI instead of hiding it.

## 🔜 What's Next

- 🧬 Swap the linear reference backbone for a **STAGATE-class graph attention
  autoencoder** through the existing model interface, and see whether the
  CauST-vs-HVG gap widens with a stronger embedding.
- 🌍 Scale the evaluation: more DLPFC slices per donor, rotating the held-out
  donor, and a second tissue/platform to test transfer beyond cortex.
- 📊 A λ-sensitivity study and the soft-reweighting variant of gene selection.
- 📦 A tagged release on PyPI plus the final report and blog.

## 🧾 Deliverables Progress

| Deliverable | Status |
| --- | --- |
| Core pipeline (knockout, invariance scoring, selection) | ✅ Completed |
| Synthetic multi-donor benchmark with HVG baseline | ✅ Completed |
| Reproducibility harness (config-driven runs, `caust verify`, determinism CI) | ✅ Completed |
| uv-managed environment, Docker image, 90%+ coverage gate | ✅ Completed |
| Real-data loader + held-out-donor benchmark (spatialLIBD DLPFC) | ✅ Completed |
| GNN backbone (STAGATE adapter) | 🟡 In Progress |
| Extended evaluation (more donors, second dataset, λ study) | ⏳ Planned |
| PyPI release, final report and blog | ⏳ Planned |

## 🙌 Closing Thoughts

The first half of the program turned CauST from a proposal into a working,
tested, reproducible package — and the midterm result I'm happiest about is not
a number but a property: every claim above can be re-earned with one command
from a fresh clone. Huge thanks to {{% mention lijinghua %}} for steering the
evaluation design toward the honest version of every experiment, and to the UC
Santa Cruz OSPO and the OSRE program for making this work possible. The
[repository](https://github.com/land-saas/CauSt) and its
[demo walkthrough](https://github.com/land-saas/CauSt/blob/main/docs/demo.md)
are open — stay tuned for the final report!
