---
title: "Midterm Reflection: Extensions to the Scenic Driving Domain"
subtitle: "Halfway through GSoC — progress, challenges, and what’s next"
summary: "A midterm reflection on my GSoC 2026 work extending Scenic’s driving domain: what I’ve accomplished so far, what I’ve learned, and where the project is headed."
authors: 
  - aprabou
tags: ["osre26", "gsoc", "probabilistic programming", "scenario specification", "uc", "simulation", "scenic"]
categories: ["GSoC 2026" , "Scenic", "Open Source"]
date: 2026-07-22
lastmod: 2026-07-22
featured: true
draft: false

image:
  focal_point: "Center"
  preview_only: false
---

Hi again! I'm Ashwin, and this is my midterm update for [Extensions to the Scenic Driving Domain](/project/osre26/ucsc/scenic) under Google Summer of Code 2026 / OSRE. I'm working with [Daniel Fremont](https://ucsc-ospo.github.io/author/daniel-fremont/) and [Eric Vin](https://ucsc-ospo.github.io/author/eric-vin/).

If you haven't seen it yet, my [introductory blog](/report/osre26/ucsc/scenic/20260505-aprabou/) covers the project goals and background. You can also find my [proposal](https://summerofcode.withgoogle.com/programs/2026/projects/7FRltlHv) here.

## Project Recap

Scenic is a probabilistic programming language for generating realistic scenarios to test systems like autonomous vehicles. My project focuses on strengthening the **driving domain**—especially OpenDRIVE map support, road-following geometry, semantic road metadata, and traffic signal–lane linkage—so scenarios are more accurate and reusable.

## Progress So Far

My proposal originally planned to spend the first few weeks on robustness—fixing known driving-domain bugs and expanding the test suite. When the project started, my mentors let me know that many of those issues had already been resolved (something also noted in the detailed proposal). Together, we reshaped the near-term plan and prioritized a new set of targets for Scenic.

With that updated roadmap, I began by extracting and populating **speed limits and road/lane types** from OpenDRIVE ([PR #484](https://github.com/BerkeleyLearnVerify/Scenic/pull/484)). From there, I moved on to **traffic signal information and signal–maneuver linkage**, so junction movements can reference their controlling signals and vice versa ([PR #491](https://github.com/BerkeleyLearnVerify/Scenic/pull/491)). Alongside that work, I’ve also started improving **left-hand-traffic (LHT) coverage**, including demo maps and validation tests ([PR #492](https://github.com/BerkeleyLearnVerify/Scenic/pull/492)).

Each of these extensions came with additions to the test suite, so the new semantic metadata and signal behavior are exercised in a reproducible way as the codebase grows.

## Challenges and Learnings

Most of the challenges I’ve faced have been about **research and fit**, not just writing code. Before changing anything, I have to dig into how a change will sit in Scenic’s compilation pipeline and how one line can ripple into other parts of the codebase. A lot of my work now starts with reading OpenDRIVE specifications and design notes long before the first commit.

Early on, I was also too focused on doing things the “right” way in an absolute sense—things like realistic road lengths or normalizing road types—when the more useful goal was simpler: **whatever the user puts in a map should come out as expected**. Seeing the problem from that user-facing perspective took time, and it slowed down my first PR. Navigating the OpenDRIVE spec itself was another hurdle; important details can be easy to miss. It took me a few days just to discover that a `<priority>` element for traffic signage even existed! Still, diving into all of this has been genuinely interesting, especially knowing the work expands what users can do with the driving domain.

I’m grateful to work with patient mentors who push me to think through solutions rather than handing them over. Communication was another early struggle: I mostly waited for our scheduled video calls, which made those meetings less productive. Over time I’ve gotten more comfortable sharing plans and updates asynchronously, so I can drive the high-level work on my own and use meeting time for the low-level details that actually need discussion. That shift has made collaboration much more effective.

One thing that surprised me was how much open-source contribution involves process—especially formatting and contribution guidelines I hadn’t really dealt with before. Learning those habits has been as much a part of the summer as the technical work itself.

## What’s Next

For the second half of the summer, I plan to focus on building out **basic traffic signal behavior**, along with **visualization and integration** with some of Scenic’s current simulators. That work is a big step toward an autopilot-style behavior in Scenic that can follow traffic signage within lanes, while also supporting the broader driving-domain goals still ahead.

## Closing Thoughts

Halfway through the summer, I’m proud of how far the driving domain work has come—and even more grateful for what I’ve learned along the way. Contributing to Scenic has stretched me as both an engineer and an open-source collaborator: I’ve gotten more comfortable reading specs, thinking about user-facing behavior, and communicating early instead of waiting for the perfect answer.

A huge thank you to Daniel and Eric for their guidance, and to UC OSPO / OSRE / GSoC for the opportunity to do this work. I’m excited for the second half of the project and looking forward to sharing more in the final blog!

Stay tuned.
