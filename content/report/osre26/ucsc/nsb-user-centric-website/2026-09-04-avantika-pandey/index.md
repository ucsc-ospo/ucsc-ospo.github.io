---

title: "GSoC 2026 Final Update: From Blank Folder to a Complete NSB Website"
subtitle: "All seven sections live, tested end to end, and ready for contributors"
summary: "Final blog wrapping up my GSoC 2026 project with UC OSPO — a user-centric documentation and onboarding website for the Network Simulation Bridge (NSB)."
authors:
  - avantika-pandey
tags: ["osre26", "gsoc26", "web-development", "open-source", "documentation", "nsb"]
categories: ["GSoC 2026", "NSB"]
date: 2026-09-04
lastmod: 2026-09-04
featured: true
draft: false
image:
  caption: ""
  focal_point: "Smart"
  preview_only: false
---

Hi again! This is my final blog post for the [NSB User-Centric Website](/project/osre26/ucsc/nsb-network-models/) project under Google Summer of Code 2026 with UC OSPO. In my [midterm update](/report/osre26/ucsc/nsb-user-centric-website/2026-07-28-avantika-pandey/), I shared how the Home, Get Started, and Quickstart pages went live. Here is how everything came together in the second half, and what the finished website looks like now.

## Picking Up After Midterm

Right after midterm, the focus shifted from "getting pages live" to "making the whole experience cohesive and complete." The site already had its core onboarding flow, but the Tutorials, Docs, Contribute, and Community sections still needed real work. The goal for the second half was to finish all seven sections, refine the content architecture, and test everything end to end as a first-time user would.

## What Got Built After Midterm

### Tutorials: Beginner, Intermediate, Advanced

The Tutorials section is now fully fleshed out across three levels:

- **Beginner**
  - *Build a Mock Simulator*: walks users through creating their own simple mock simulator using the NSB client.
  - *Experiment with the Mock Simulator*: shows how to run the mock, fetch entries, and observe message flow.
- **Intermediate**
  - *NetworkX Graph Simulator*: introduces a slightly more realistic simulator using NetworkX to model graph-based communication.
- **Advanced**
  - *NS-3 Integration*: step-by-step guide to plugging NSB into NS-3.
  - *OMNeT++ Basic Integration* and *OMNeT++ INET Integration*: detailed instructions for connecting NSB to OMNeT++ with the INET framework.

These pages turned abstract "advanced simulators" into concrete, reproducible workflows that contributors can follow and adapt.

### Docs: Architecture, Protocol, API, and Navigation

The Docs section grew significantly:

- Added and refined **architecture diagrams** for different operating modes and system configurations.
- Introduced **protocol and integration diagrams** to clarify how clients, the daemon, and simulators interact.
- Added an **"On This Page"** right-side navigation to make long documentation pages easier to skim and navigate.
- Updated **Python API reference** for message entry, app client, and simulation client, with clearer examples and organization.
- Fixed broken **Quickstart links** and improved consistency in code block styling across Docs and Getting Started.

A small but important detail: we kept iterating on the architecture illustration on the About page until the app and simulator boxes, connectors, and message flow felt immediately understandable at a glance.

### Contribute and Community Pages

Two new pages rounded out the site:

- **Contribute**: explains how to contribute to NSB, with clear paths for code, docs, and feedback. It now includes a **live GitHub issue feed** that pulls open issues directly from the NSB repository, so contributors can see current opportunities without leaving the site.
- **Community**: describes how to connect with other contributors, where discussions happen, and how to stay updated on NSB developments.

These pages turn the website from "documentation only" into a real entry point for the contributor community.

### Polish and Maintenance Work

Alongside new content, there was steady refinement:

- Updated all **Docusaurus packages** to 3.10.2 to resolve version mismatch errors during build.
- Clarified the **daemon verification step** in Get Started to emphasize starting from a valid `config.yaml`.
- Standardized terminology (for example, consistently using "mock simulator" instead of "pre-built simulator").
- Improved explanations of **per-node vs system-wide modes** and simulator identifiers in the tutorials.
- Added a dedicated **README for the website directory** to help future contributors understand the site structure and how to work on it.

## Testing: Making Sure It All Actually Works

The last major phase was comprehensive testing, split into multiple rounds:

- **Functional testing**: checked all navigation links, buttons, and cross-page references to ensure nothing was broken or leading to dead ends.
- **Onboarding flow testing**: walked through Get Started and Quickstart exactly as a new user would, from zero to first successful message exchange.
- **Tutorial validation**: set up each tutorial locally (mock simulator, NetworkX, NS-3, OMNeT++) and ran the full simulations to confirm the instructions were correct and complete.
- **Documentation consistency**: verified that terminology, code examples, and diagrams were consistent across Docs, Tutorials, and Quickstart.

The testing notes followed a uniform pattern: commands run, expected result, actual result, status, and observations. This made it easier to catch small mismatches between what the docs said and what actually happened on a fresh setup.

## Where the Project Ended Up

By the end of GSoC, the NSB website has:

- All **seven sections** complete: Home, About, Get Started, Quickstart, Docs, Tutorials, Contribute, and Community.
- A clear **contributor journey** from discovery to first success to deeper involvement.
- **Progressive learning** from a simple mock simulator up to NS-3 and OMNeT++ integrations.
- Live, tested documentation that a new contributor can follow locally and reproduce step by step.

The site is deployed at: [https://nsb-ucsc.github.io/nsb/](https://nsb-ucsc.github.io/nsb/)

## What This Project Taught Me

This project reinforced that good documentation is not about explaining everything at once. It is about designing a path where someone can:

- See what NSB is and why it matters.
- Get a working example running quickly.
- Understand enough architecture to feel oriented.
- Then choose their own next step: deeper tutorials, API deep dives, or contributing back.

Watching a first-time user go from "I have no idea where to start" to "I ran a simulation and saw messages moving" in under 15 minutes was the best validation I could ask for.

## Thank You

Huge thanks to my mentor **Harikrishna (Hari) Kuttivelil** for the guidance, design discussions, and patience through countless iterations. Thank you to **UC OSPO** for the opportunity and support throughout the summer, and to the NSB team for feedback and collaboration.

If you are exploring NSB or thinking about contributing, the website is ready for you. And if you would like to connect, you can find me on [LinkedIn](https://www.linkedin.com/in/avantika-pandey-4430512b4) or [GitHub](https://github.com/avantika1036).
