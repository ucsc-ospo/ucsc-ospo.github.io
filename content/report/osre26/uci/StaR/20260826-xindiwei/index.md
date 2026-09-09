---
title: "GSoC 2026 Final Work Product — StaR"
date: 2026-08-26
authors: ["xindiwei"]
tags: ["osre26", "reproducibility"]
summary: "A stability-aware representation learning framework for spatial domain identification."
---

**Contributor:** Xindi Wei
**Mentor:** Ziheng Duan
**Organisation:** UC Santa Cruz Open Source Program Office (UC OSPO) / OSRE 2026
**Project:** StaR — A Stability-Aware Representation Learning Framework for Spatial Domain Identification
**Code:** this repository ([`star/`](star/), [`scripts/`](scripts/), [`slurm/`](slurm/))
**License:** MIT

> **In one sentence:** we showed that state-of-the-art spatial-domain methods
> are far more sensitive to the random seed than the published gaps between
> them, and we built a model — StaR — that removes most of that sensitivity
> while also being the most accurate of the six methods compared.

If you only read one thing, read **[Results](#3-results)**; if you only run one
thing, run `python scripts/smoke_test.py`.

---

## 1. Project goals

The proposal set out to address a reproducibility problem in spatial
transcriptomics. Graph neural network (GNN) methods for **spatial domain
identification** — partitioning a tissue section into biologically coherent
regions — are benchmarked as if they were deterministic, but their output
depends on the random seed. The proposed goals were:

1. Quantify seed sensitivity across leading GNN methods at a scale large enough
   to be conclusive.
2. Implement a **deterministic spatial prior** that all seeds are pulled toward.
3. Integrate it into a variational objective via **KL regularisation**.
4. Add optimisation-side stabilisers (β-annealing, Stochastic Weight Averaging).
5. Run **comprehensive benchmarking and mechanistic ablations**.

All five were completed. Goal 4 completed with a negative result, which is
reported as such — see [§6](#6-challenges-and-lessons-learned).

---

## 2. What was delivered

| # | Deliverable | State |
|---|---|---|
| 1 | Seed-sensitivity study: 6 methods × 1,000 seeds × 12 DLPFC sections (72,000 training runs) | ✅ Complete |
| 2 | StaR model: structured spatial prior + VGAE ([`star/model.py`](star/model.py)) | ✅ Complete |
| 3 | Benchmark against 5 published baselines under an identical protocol | ✅ Complete |
| 4 | Leave-one-out component ablation + α/β hyperparameter sweeps | ✅ Complete |
| 5 | Mechanistic follow-ups: prior-only probe, gene-coverage sweep, K-robustness | ✅ Complete |
| 6 | Cross-platform generalisation: MOSTA Stereo-seq mouse hemibrain | ✅ Complete |
| 7 | Open-source release: installable package, runners, SLURM wrappers, smoke test | ✅ Complete |
| 8 | Broader multi-platform benchmarking (Xenium, MERFISH, non-brain tissue) | ⏳ Future work |
| 9 | Structured prior as a drop-in stabiliser for other backbones | ⏳ Future work |

---

## 3. Results

### 3.1 Seed sensitivity is large enough to invalidate single-seed benchmarks

Five published methods were run with **1,000 independent seeds on each of the
12 DLPFC sections**. Pooled coefficient of variation (CV) of ARI ranges from
14.4% to 27.0%. On section 151669 STAGATE reaches **CV = 28.4%** — roughly a
third of its reported accuracy is seed noise, which is larger than the
published gaps between competing methods.

### 3.2 StaR: accuracy and worst-case reproducibility

DLPFC, all six methods, 1,000 seeds × 12 sections (12,000 pooled runs each):

| Method | Mean ARI | Median | P5 (worst) | P95 (best) | Std | CV (%) |
|---|:--:|:--:|:--:|:--:|:--:|:--:|
| SpaGCN | 0.338 | 0.334 | 0.205 | 0.500 | 0.091 | 27.0 |
| SpaceFlow | 0.435 | 0.430 | 0.265 | 0.638 | 0.114 | 26.2 |
| stCluster | 0.435 | 0.432 | 0.264 | 0.585 | 0.100 | 23.0 |
| STAGATE | 0.488 | 0.495 | 0.246 | 0.642 | 0.123 | 25.2 |
| GraphST | 0.506 | 0.502 | 0.398 | 0.606 | **0.073** | **14.4** |
| **StaR** | **0.542** | **0.536** | **0.417** | **0.659** | 0.090 | 16.6 |

StaR leads on mean, median, P5 and P95, and beats the strongest baseline
(GraphST) on **all 12 sections** (Wilcoxon signed-rank *p* = 0.0002). Note the
honest caveat: StaR is *not* the lowest-variance method — GraphST is — but
StaR's distribution stochastically dominates GraphST's at every percentile,
so the wider spread is upward reach, not downside risk.

### 3.3 Ablation: the structured prior does the work

Leave-one-out on the full benchmark (12 sections × 50 seeds):

| Configuration | Mean ARI | ΔARI | Mean CV (%) | *p* (full > ablated) |
|---|:--:|:--:|:--:|:--:|
| **Full StaR** | **0.543** | — | 9.1 | — |
| − Structured prior → 𝒩(0, I) | 0.307 | −0.236 | 22.8 | 0.0002 |
| − Spatial label refinement | 0.526 | −0.017 | 8.8 | 0.0002 |
| − β-annealing | 0.544 | +0.001 | 9.8 | 0.63 (n.s.) |
| − Stochastic Weight Averaging | 0.544 | +0.001 | 8.7 | 0.63 (n.s.) |

Removing the structured prior collapses accuracy and **more than doubles**
inter-seed CV. The two optimisation-side stabilisers do nothing measurable.

### 3.4 Two follow-ups that sharpen the story

- **Clustering the prior directly** — no VAE training at all — already reaches
  0.534 mean ARI on DLPFC, above every baseline, at *zero* seed variance.
- **The VAE earns its keep when genes are scarce.** As highly variable genes
  drop from 3,000 (Visium) to 200 (targeted-panel / imaging scale), the static
  prior collapses while StaR holds: the gap grows from +0.015 to
  **+0.277 ARI**.

### 3.5 Generalisation to a different platform and tissue

MOSTA Stereo-seq adult mouse hemibrain (10,000 spots, 19 anatomical regions),
20 seeds, **using the DLPFC hyperparameters unchanged**:

| Method | Mean ARI | P5 (worst) | CV (%) |
|---|:--:|:--:|:--:|
| **StaR** | **0.585** | **0.546** | **4.0** |
| SpaGCN | 0.484 | 0.413 | 10.5 |
| STAGATE | 0.421 | 0.383 | 4.9 |
| GraphST | 0.391 | 0.302 | 15.2 |
| SpaceFlow | 0.314 | 0.245 | 14.9 |
| stCluster | 0.261 | 0.180 | 23.6 |

StaR's *worst* 5% of seeds still beat the *mean* of every other method.

---

## 4. The code contribution

Everything in this repository is work produced for this project. Nothing is
vendored from upstream projects; the baselines are invoked through their own
published packages.

### 4.1 Library — [`star/`](star/)

| File | What it contains |
|---|---|
| [`star/model.py`](star/model.py) | The method. `StaR` encoder/decoder (GAT), `compute_spatial_prior` (the deterministic graph-diffusion anchor), `kl_divergence_structured` (KL against a non-zero prior mean), `train_star` (training loop with β-annealing and SWA), `mclust_labels` (fixed-seed Mclust readout), `spatial_label_refine` (neighbourhood majority vote). |
| [`star/paths.py`](star/paths.py) | Dataset/result roots, overridable with `STAR_DATA_ROOT`, `STAR_STEREOSEQ_ROOT`, `STAR_RESULTS_ROOT`, so the code runs off the machine it was developed on. |

The core idea in two lines:

```
mu_prior = (I + alpha * L_norm)^{-1} PCA(X)      # deterministic, identical for every seed
ELBO     = || X - X_hat ||^2  +  beta * KL( q(z|X,G) || N(mu_prior, I) )
```

Library defaults are the canonical configuration behind every number in
[§3](#3-results) (`alpha=0.5`, `beta_max=0.05`, SWA from epoch 600, 800 epochs,
Mclust seed 2020), so `train_star(data, adata)` with no arguments reproduces
the reported setup.

### 4.2 Experiments — [`scripts/`](scripts/)

| File | Produces |
|---|---|
| [`scripts/smoke_test.py`](scripts/smoke_test.py) | 30-second synthetic end-to-end check; needs no dataset, and demonstrates the prior's stabilising effect in miniature. |
| [`scripts/experiments/seed_sensitivity/`](scripts/experiments/seed_sensitivity/) | The 1,000-seed sweeps for STAGATE, GraphST, SpaceFlow, stCluster. |
| [`scripts/experiments/star_v2/run_star_1000.py`](scripts/experiments/star_v2/run_star_1000.py), [`run_spagcn_1000.py`](scripts/experiments/star_v2/run_spagcn_1000.py) | The 1,000-seed runs for StaR and SpaGCN. |
| [`scripts/experiments/star_v2/run_star_improve.py`](scripts/experiments/star_v2/run_star_improve.py) | The canonical 50-seed configuration sweep the ablation and β sweep are measured against. |
| [`scripts/experiments/star_v2/run_star_ablation.py`](scripts/experiments/star_v2/run_star_ablation.py), [`run_beta_alpha05.py`](scripts/experiments/star_v2/run_beta_alpha05.py) | Leave-one-out ablation, α and β sweeps. |
| [`scripts/experiments/star_v2/ablation_prior_only.py`](scripts/experiments/star_v2/ablation_prior_only.py), [`ablation_prior_probe.py`](scripts/experiments/star_v2/ablation_prior_probe.py) | The prior-only probe (§3.4). |
| [`scripts/experiments/star_v2/ablation_hvg.py`](scripts/experiments/star_v2/ablation_hvg.py) | Gene-coverage sweep, HVG 3,000 → 200. |
| [`scripts/experiments/star_v2/run_k_robustness.py`](scripts/experiments/star_v2/run_k_robustness.py) | Sensitivity to a misspecified cluster count (K ± 1). |
| [`scripts/experiments/star_v2/run_mosta_hemibrain.py`](scripts/experiments/star_v2/run_mosta_hemibrain.py), [`run_hemibrain_baselines.py`](scripts/experiments/star_v2/run_hemibrain_baselines.py), [`run_gen_extra_baselines.py`](scripts/experiments/star_v2/run_gen_extra_baselines.py), [`run_hemibrain_fig20.py`](scripts/experiments/star_v2/run_hemibrain_fig20.py) | The six-method Stereo-seq generalisation study. |
| [`scripts/analyze_1000seed.py`](scripts/analyze_1000seed.py) | Aggregates the per-seed CSVs into every table in §3 (mean/median/P5/P95/Std/CV and the Wilcoxon tests). |
| [`scripts/figures/`](scripts/figures/) | Figures for the results in [§3](#3-results). |
| [`scripts/run_star_dlpfc.py`](scripts/run_star_dlpfc.py) | Self-contained single-file DLPFC reproduction, for readers who want the method without the package. |
| [`slurm/`](slurm/) | SLURM array wrappers for every experiment above. |

---

## 5. Reproducing the work

```bash
git clone https://github.com/GITHUB_USER/StaR.git
cd StaR
conda create -n star python=3.8 -y && conda activate star
pip install -r requirements.txt && pip install -e .
# R side, for the Mclust readout:  install.packages("mclust")

# 1. Verify the install (no dataset needed, ~30 s on CPU)
python scripts/smoke_test.py

# 2. Point at the data (see README for where to download it)
export STAR_DATA_ROOT=/path/to/10XVisium/DLPFC

# 3. Reproduce the main benchmark, then the tables
sbatch slurm/sbatch_star_1000.sh
python scripts/analyze_1000seed.py
```

Every result in §3 is derived from per-seed ARI CSVs written by the runner
scripts; `analyze_1000seed.py` recomputes the tables from those CSVs, so a
reviewer can check the statistics without re-running 72,000 trainings.
A single StaR run on one DLPFC section (≈4,000 spots, 800 epochs) takes
about 1.5 minutes on an A100, comparable to STAGATE.

---

## 6. Challenges and lessons learned

**Compute orchestration at benchmark scale.** 72,000 training runs on a shared
SLURM cluster only works if every job is resumable. The runners checkpoint to
per-seed CSVs and skip completed seeds on restart, so a pre-empted node costs
minutes rather than days.

**Making the comparison genuinely fair.** A stability claim is worthless if the
comparison is rigged. Every baseline runs with its authors' recommended
settings, its own seed propagated through NumPy, PyTorch *and* R, and the same
Mclust readout with a fixed clustering seed — so the variance we report comes
from network initialisation alone, not from the clustering step. A large share
of the project went into this rather than into the model.

**The ablation contradicted part of the proposal, and that became a result.**
The proposal weighted the deterministic prior, KL regularisation and the
optimisation tricks (SWA, β-annealing) roughly equally. The ablation showed the
optimisation tricks contribute nothing measurable (Δ ARI = +0.001, *p* = 0.63)
and the prior does essentially all the work. They are kept in the codebase as
optional, off-by-default-irrelevant components and reported honestly rather than
quietly retained as decoration.

**Red-teaming our own method produced the most interesting finding.** Asking
"what if the VAE isn't needed at all?" showed the deterministic prior alone
nearly matches the full model on Visium data. Rather than bury that, we went
looking for the regime where the VAE *does* matter and found it: sparse gene
coverage, where the gap grows to +0.277 ARI. That result only exists because we
tried to falsify our own contribution.

---

## 7. Current state and what remains

**Working today:** the model, all six-method benchmarks, the ablations, the
generalisation study and every figure and table can be regenerated from this
repository given the public datasets.

**Known limitations, stated plainly:**

- The prior is built from a dense pairwise distance matrix, which is O(N²) in
  memory. It is fine up to ~10,000 spots but needs a sparse/k-NN formulation
  for whole-slide imaging-based data.
- Hyperparameters (α = 0.5, β_max = 0.05) were tuned on DLPFC only and carried
  over unchanged elsewhere. They transfer well to Stereo-seq, but this is one
  transfer, not a guarantee.
- Generalisation evidence beyond DLPFC currently rests on a single additional
  dataset.
- The number of domains K is supplied by the user, as with all compared methods.

**Next steps, in priority order:**

1. Sparse k-NN prior construction to lift the O(N²) ceiling.
2. Broader benchmarking across platforms and organisms (Xenium, MERFISH,
   non-brain tissue).
3. Test the structured prior as a drop-in stabiliser inside other backbones
   (STAGATE, GraphST) — the original "plug-in framework" ambition of the
   proposal, now with evidence about which component to plug in.

Anyone picking this up should start at [`star/model.py`](star/model.py);
items 2 and 4 are both localised to `compute_spatial_prior`.

---

## 8. Data availability

No data is redistributed here. The DLPFC benchmark (12 × 10x Visium sections,
151507–151676) comes from [spatialLIBD](http://spatial.libd.org/spatialLIBD/);
the generalisation dataset is the MOSTA Stereo-seq adult mouse hemibrain.
Point `STAR_DATA_ROOT` and `STAR_STEREOSEQ_ROOT` at your local copies.

## 9. Acknowledgements

Thanks to my mentor **Ziheng Duan** for the guidance and compute, and to UC OSPO
/ CROSS and the OSRE 2026 program for supporting this work.
