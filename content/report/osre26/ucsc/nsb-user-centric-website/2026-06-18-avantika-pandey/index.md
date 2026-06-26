---
title: "Developing a User-Centric Website for the Network Simulation Bridge"
subtitle: "What if setting up NSB took 15 minutes instead of 4 hours?"
summary: "First blog introducing my GSoC 2026 project with UC OSPO — building a user-centric documentation and onboarding website for the Network Simulation Bridge (NSB)."
authors:
  - avantika-pandey
tags: ["osre26", "gsoc26", "web-development", "open-source", "documentation"]
categories: []
date: 2026-06-18
lastmod: 2026-06-18
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "Smart"
  preview_only: false
---

Hi! Thanks for stopping by.

In this first blog post of a series of three, I'd like to introduce myself, my mentor, and my project.

My name is Avantika Pandey — a third-year Computer Science student at UIET, Panjab University Chandigarh, with a background in full-stack web development and open source contribution. This summer, I am contributing to the [NSB User-Centric Website](/project/osre26/ucsc/nsb-network-models/) project as part of Google Summer of Code 2026 under UC OSPO. I am very grateful to be mentored by **Harikrishna Kuttivelil**. Feel free to read my accepted [GSoC proposal](https://drive.google.com/file/d/19th4sjon1kRAxhi6R-FgpfXns9csxWUk/view?usp=drive_link) and browse the [wireframe prototype](https://avantika1036.github.io/NSB-Wireframe/) I built before writing the proposal.

## The Problem

The [Network Simulation Bridge (NSB)](https://github.com/nsb-ucsc/nsb) is a middleware layer that connects real application code to network simulators — letting developers and researchers test distributed systems under controlled network conditions (specific latency, packet loss, topology) without needing real infrastructure. NSB is technically solid. Its Python and C++ API documentation is detailed and well-written.

But here is the catch: **none of that is easy to find.**

After reading every file in the NSB repository and tracing the full setup sequence from scratch as a first-time user, I identified a single root cause behind multiple surface-level problems: there is no guided path from *"I just found NSB"* to *"I have a working example running."* No quickstart, no architecture diagram, undocumented config fields, and eight prerequisites before a single line of user code runs. The result: getting NSB running for the first time takes an estimated **3–4 hours**. The goal of this project is to bring that down to **15 minutes**.

## The Project

My project builds a complete 7-section public website for NSB: **Home → Get Started → Quickstart → Docs → Tutorials → Contribute → Community**. Every design decision is guided by one principle: *First Success First* — get the user to a working NSB message exchange before asking them to understand anything. Once they have seen it work, documentation stops being an obstacle and starts being a resource.

A few key decisions that shape the project:

- The **Quickstart** ships with a pre-built mock simulator so a first-time user can observe a full message round-trip without writing a single line of simulator code — both endpoints provided, out of the box.
- **Simulator integration** (NS-3, OMNeT++) is deliberately deferred to the Tutorials section, introduced after the user already has a working foundation.
- **Windows users** get a dedicated WSL2 tab on the Get Started page with step-by-step instructions.
- The **Docs section** fully annotates every `config.yaml` field, adds a troubleshooting guide with 20+ error/fix pairs, and unifies the Python and C++ API reference into one searchable hub.

## Expected Deliverables

- Complete NSB website — all 7 sections, publicly deployed, responsive on desktop and mobile
- Quickstart onboarding — platform-specific install guide (macOS, Linux, Windows WSL2) with a clear 15-minute path to first message exchange
- Structured documentation hub — full `config.yaml` reference, unified Python/C++ API docs, architecture and message flow diagrams in Mermaid
- Tutorial series — Beginner, Intermediate (user builds their own mock with NetworkX), and Advanced (NS-3 / OMNeT++ integration)
- Contributor infrastructure — `CONTRIBUTING.md`, Good First Issues list, PR/issue templates
- Usability validation report — measured time-to-first-success with real first-time users

Stay tuned for the midterm and final posts — there is a lot to build, and I am excited to share how it unfolds!

If you find this work interesting, feel free to connect on [LinkedIn](https://www.linkedin.com/in/avantika-pandey-4430512b4) or follow along on [GitHub](https://github.com/avantika1036). Great to meet the UC OSPO community — thanks for reading!