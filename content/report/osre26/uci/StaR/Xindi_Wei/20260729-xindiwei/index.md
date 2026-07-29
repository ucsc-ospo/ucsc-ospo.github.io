---
title: "Halfway Through GSoC: Making Spatial Domain Identification Reproducible"
subtitle: "StaR: A Stability-Aware Representation Learning Framework for Spatial Domain Identification"
summary: "A mid-term update on StaR — the largest seed-sensitivity study of spatial-domain methods to date (6 methods x 1,000 seeds x 12 tissue sections), and SpaGVAE, the structured-spatial-prior model we built to fix the instability we found."
authors:
  - xindiwei
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

As part of the **StaR** project, my proposal under the mentorship of [Ziheng Duan](https://ucsc-ospo.github.io/author/ziheng-duan/) set out to tackle a problem that is easy to overlook but hard to unsee once you have measured it: state-of-the-art graph neural network (GNN) methods for spatial domain identification give *different answers depending on the random seed*, and the size of that variation can rival the reported gap between competing methods.

The first half of GSoC went into (1) measuring exactly how bad the problem is, and (2) building a model that fixes it. Both are now done, and the work has been written up as a full manuscript with an accompanying open-source release.

## 🚀 Achievements

### ✅ The largest seed-sensitivity study of spatial domain methods to date

To establish the problem quantitatively rather than anecdotally, I benchmarked five published GNN methods — **STAGATE, GraphST, SpaceFlow, stCluster and SpaGCN** — with **1,000 independent random seeds each, on all 12 DLPFC tissue sections**. That is 60,000 training runs in total, orchestrated on a SLURM cluster.

The results confirmed the premise of the proposal and then some. Pooled across all seeds and sections, the coefficient of variation (CV) of the Adjusted Rand Index (ARI) ranges from **14.4% to 27.0%** depending on the method. Instability is also unevenly distributed: on section 151669, STAGATE reaches **CV = 28.4%**, meaning nearly a third of its reported accuracy is seed noise. In practice this means a single-seed benchmark can rank two methods in either order.

### ✅ Built SpaGVAE — a variational graph autoencoder with a structured spatial prior

The framework I proposed as StaR evolved during implementation into **SpaGVAE (Spatial Graph Variational AutoEncoder)**, and the mechanism became sharper than the original proposal anticipated. The core idea: replace the standard isotropic Gaussian prior of a VAE with a **deterministic, seed-independent spatial anchor** obtained by graph diffusion of PCA embeddings.

```
mu_prior = (I + alpha * L_norm)^{-1} PCA(X)          # deterministic, identical for every seed
ELBO     = || X - X_hat ||^2  +  beta * KL( q(z|X,G) || N(mu_prior, I) )
```

Because every seed is pulled toward the *same* spatial reference, different runs can no longer settle into unrelated solutions.

### ✅ Benchmarked SpaGVAE against all five baselines under the same 1,000-seed protocol

| Method | Mean ARI | Worst-case (P5) ARI | CV (%) |
|---|:--:|:--:|:--:|
| SpaGCN | 0.338 | 0.205 | 27.0 |
| SpaceFlow | 0.435 | 0.265 | 26.2 |
| stCluster | 0.435 | 0.264 | 23.0 |
| STAGATE | 0.488 | 0.246 | 25.2 |
| GraphST | 0.506 | 0.398 | 14.4 |
| **SpaGVAE** | **0.542** | **0.417** | 16.6 |

SpaGVAE has the highest mean ARI, and — more importantly for reproducibility — the highest **worst-case** ARI: even in its unluckiest 5% of seeds it beats every baseline's worst case. It outperforms the strongest baseline (GraphST) on **all 12 sections** (Wilcoxon signed-rank *p* = 0.0002). Notably, SpaGVAE is *not* the lowest-variance method (GraphST is), but its whole ARI distribution sits above GraphST's at every percentile, so its wider spread is upward reach rather than downside risk.

### ✅ Mechanistic ablations and generalisation tests

A leave-one-out ablation (12 sections × 50 seeds) isolates *why* the method works. Removing the structured prior collapses mean ARI from 0.542 to **0.307** and more than doubles inter-seed variability, whereas removing β-annealing or Stochastic Weight Averaging leaves both essentially unchanged. The structured prior is the workhorse.

Two follow-ups sharpened this further:

- **Clustering the deterministic prior directly**, with no VAE training at all, already reaches 0.534 mean ARI on DLPFC — above every baseline, at *zero* seed variance. This was a humbling result to find in our own method.
- **The VAE earns its keep when genes are scarce.** As highly variable genes drop from 3,000 (Visium scale) to 200 (targeted-panel / imaging scale), the static prior collapses while SpaGVAE holds up; the gap widens from +0.015 to **+0.277 ARI**.

For generalisation, I evaluated all six methods on the **MOSTA Stereo-seq adult mouse hemibrain** (10,000 spots, 19 annotated anatomical regions) — a different platform, tissue and labelling scheme — using the DLPFC hyperparameters unchanged. SpaGVAE leads with mean ARI **0.585** vs. 0.484 (SpaGCN), 0.421 (STAGATE) and 0.391 (GraphST), while also being the most stable (CV 4.0%).

### ✅ Manuscript and open-source release

The work is written up as a full manuscript, *"SpaGVAE: A Variational Graph Autoencoder with Structured Spatial Prior for Robust Spatial Domain Identification,"* currently in preparation for submission to *BMC Bioinformatics*. A reference implementation — training code, all baseline wrappers, SLURM scripts and figure-reproduction notebooks — is being prepared for public release under the MIT license at [github.com/RRRussell/StaR](https://github.com/RRRussell/StaR).

## 🧠 Challenges

**Compute scale.** Running six methods × 1,000 seeds × 12 sections is 72,000 training runs. Getting this through a shared SLURM cluster meant building checkpoint-resumable job arrays, careful memory budgeting, and result caching so that a failed node never cost more than a handful of runs.

**Being fair to the baselines.** A stability claim is worthless if the comparison is rigged. Every baseline had to be run with its authors' recommended settings, its own seed properly propagated through NumPy/PyTorch/R (Mclust seeds are a genuine footgun here), and the same clustering back-end. A good fraction of the first half went into making sure that when SpaGVAE wins, it wins for real reasons.

**My own method surprised me.** The original proposal put roughly equal weight on the deterministic prior, KL regularisation, and "advanced optimisation techniques" (SWA, β-annealing). The ablation said otherwise: the optimisation tricks contribute essentially nothing, and the prior does all the work. Rather than quietly keeping the extra components as decoration, we report the ablation honestly and reframed the paper's story around the prior. The related finding — that the prior alone can nearly match the full model on Visium data — pushed us to find the regime where the VAE genuinely matters (sparse gene coverage), which is now one of the more interesting results in the paper.

## 🔜 What's Next

- 📝 Finish and submit the manuscript to *BMC Bioinformatics*
- 📦 Polish the public release: documentation, tutorial notebook, PyPI packaging, and a one-command reproduction script for every figure and table
- 🧬 Broaden the generalisation benchmark to more platforms and organisms (10x Xenium, MERFISH, non-brain tissues)
- 🔍 Push further on the sparse-gene-coverage regime, which is where imaging-based spatial transcriptomics is heading and where SpaGVAE's advantage is largest
- 📉 Investigate whether structured spatial anchoring can be dropped into other backbones (STAGATE, GraphST) as a plug-in stabiliser, which was the original "framework" ambition of the proposal

## 🧾 Deliverables Progress

| Deliverable | Status |
|---|---|
| Large-scale seed-sensitivity study (6 methods × 1,000 seeds × 12 sections) | ✅ Completed |
| Deterministic spatial prior | ✅ Completed |
| KL regularisation & training objective | ✅ Completed |
| Advanced optimisation (SWA, β-annealing) | ✅ Implemented — ablation shows negligible effect |
| Comprehensive benchmarking vs. 5 baselines | ✅ Completed |
| Mechanistic ablations & hyperparameter sweeps | ✅ Completed |
| Cross-platform generalisation (Stereo-seq) | ✅ Completed |
| Manuscript | 🟡 In preparation |
| Open-source release & documentation | 🟡 In progress |
| Broader multi-platform benchmarking | ⏳ Planned |
| Plug-in stabiliser for other backbones | ⏳ Planned |

## 🙌 Closing Thoughts

The most valuable thing I learned this summer was not a modelling technique — it was how much a field can rest on numbers that move when you change a seed. Measuring that carefully turned out to be as much of a contribution as the model we built to fix it, and running the ablation that undercut part of my own proposal was, in retrospect, the moment the project got good.

Huge thanks to my mentor **Ziheng Duan** for the guidance, the compute, and for consistently pushing me to check whether my own results actually meant what I thought they meant.

If you work on spatial transcriptomics — or on reproducibility in ML benchmarks more generally — I'd love to hear from you.
