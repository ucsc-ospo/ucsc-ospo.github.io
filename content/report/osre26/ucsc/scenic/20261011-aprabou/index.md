---
title: "Final Reflection: Extensions to the Scenic Driving Domain"
subtitle: "Wrapping up GSoC — what shipped, what I learned, and what’s next"
summary: "A final reflection on my GSoC 2026 work extending Scenic’s driving domain, with gratitude for my mentors and UC OSPO / OSRE."
authors: 
  - aprabou
tags: ["osre26", "gsoc", "probabilistic programming", "scenario specification", "uc", "simulation", "scenic"]
categories: ["GSoC 2026" , "Scenic", "Open Source"]
date: 2026-10-11
lastmod: 2026-10-11
featured: true
draft: false

image:
  focal_point: "Center"
  preview_only: false
---

Hi again! I'm Ashwin, and this is my final update for [Extensions to the Scenic Driving Domain](/project/osre26/ucsc/scenic) under Google Summer of Code 2026 / OSRE, mentored by [Daniel Fremont](https://ucsc-ospo.github.io/author/daniel-fremont/) and [Eric Vin](https://ucsc-ospo.github.io/author/eric-vin/).

You can find my [introductory blog](/report/osre26/ucsc/scenic/20260505-aprabou/), [midterm reflection](/report/osre26/ucsc/scenic/20260722-aprabou/), [proposal](https://summerofcode.withgoogle.com/programs/2026/projects/7FRltlHv), and [final report](https://gist.github.com/aprabou/0ca95f71491934f0ad90dfd29ba4b392) here.

## Looking Back

Over the summer I focused on making Scenic’s OpenDRIVE-backed driving domain more useful for scenario authors. The main deliverables landed as open PRs now in final review:

- **Semantic tags, speed limits, and road metadata** ([PR #484](https://github.com/BerkeleyLearnVerify/Scenic/pull/484)) — so authors can select roads by tag and look up speed limits along a road, instead of hand-building regions for those properties.
- **Signal semantics and lane-specific halt points** ([PR #498](https://github.com/BerkeleyLearnVerify/Scenic/pull/498), consolidating earlier signal–maneuver work from [#491](https://github.com/BerkeleyLearnVerify/Scenic/pull/491)) — so behaviors can query where to stop for the signal governing a lane, not just where the pole sits.
- **Left-hand-traffic fixtures and tests** ([PR #492](https://github.com/BerkeleyLearnVerify/Scenic/pull/492), draft) — ready once the parser honors `rule="LHT"`.

Larger pieces — especially the Frenet-frame geometry API, curvature-aware lane following, and a Scenic autopilot that stops at red lights — didn’t fit the window. I plan to keep contributing after GSoC to finish them.

## Reflection

The biggest lesson was **API minimalism** in a shared codebase. My first pass at #484 leaned on helpers and heuristics that felt natural while writing, but review pushed me toward setting tags and limits directly at construction time and cutting anything that wasn’t clearly needed. I also learned to scope PRs around a single capability rather than how the work unfolded day-to-day, and to leave dependent work (like LHT tests) in draft until the underlying support exists.

## Gratitude

Thank you to Daniel and Eric for patient, detailed review on every PR — it taught me more about maintaining a research codebase than I would have learned alone. I’m also grateful to UC OSPO / OSRE and Google Summer of Code for the chance to contribute to Scenic this summer.

I’m looking forward to continuing the Frenet-frame and autopilot work beyond the program. Thanks for following along!
