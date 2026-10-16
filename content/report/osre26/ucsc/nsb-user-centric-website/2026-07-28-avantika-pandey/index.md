---
title: "My GSoC Midterm Update: From Setup Struggles to a Deployed Site"
subtitle: "From a blank folder to a deployed website with a Quickstart, docs, and a glowing new architecture diagram"
summary: "Midterm blog for my GSoC 2026 project with UC OSPO — progress on the NSB user-centric website, from onboarding and setup to a fully deployed site with Home, Get Started, Quickstart, and Docs pages taking shape."
authors:
  - avantika-pandey
tags: ["osre26", "gsoc26", "web-development", "open-source", "documentation"]
categories: ["GSoC 2026", "NSB"]
date: 2026-07-28
lastmod: 2026-07-28
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "Smart"
  preview_only: false'
---

Hi again! It has been a little over two months since I introduced myself and my project — the [NSB User-Centric Website](/project/osre26/ucsc/nsb-network-models/) — in my first blog. This is my midterm update, and there is a lot to share.

The website is now live at **[nsb-ucsc.github.io/nsb](https://nsb-ucsc.github.io/nsb/)**, with the Home, Get Started, and Quickstart pages complete, and the Docs section well underway. Here is how it came together.

## Getting the Foundation Right

Community bonding was less about writing code and more about becoming an NSB user myself. I set up NSB from scratch on Windows with WSL, worked through protobuf and Abseil dependency issues, built the NSB core, and verified the daemon and runtime end to end — documenting every point of friction along the way. That process shaped the entire project, because the problems I hit as a first-time user became the exact problems the website needed to solve.

Alongside setup, I dug into the architecture: how application clients, the NSB daemon, the SocketRTScheduler, and OMNeT++ all talk to each other through protobuf messaging and socket channels. This groundwork made the design conversations that followed much easier to reason about.

## Designing Before Building

Before writing a single line of website code, my mentor **Harikrishna (Hari) Kuttivelil** and I spent real time on the presentation and design direction. I put together a full website structure deck, and during a team review, we landed on the visual identity: **navy blue and gold for dark mode, turquoise cyan for light mode**. We also sent out a feedback form to the wider team to validate the color scheme before committing to it, rather than guessing.

One design decision worth calling out: the mock simulator does not try to simulate a full NSB environment inside the browser. Instead, it is shipped as a downloadable file — simpler, honest about what a browser can and cannot do, and much easier for a new user to actually run.

## Building the Pages, One at a Time

**Home page.** Week 1 went into the site structure and an animated hero illustration. It evolved more than once — we later reduced the amount of content on Home and moved the deeper explanations to a dedicated About page, keeping the first impression focused and light. The hero diagram also got a redesign: instead of the original architecture diagram, it now shows separate app and simulator boxes connected by **glowing payloads** — a small detail, but one that makes the "what does NSB actually do" question click visually before a user reads a word.

**Get Started.** This page took the most rethinking. Writing content by working through the repository's READMEs and the latest NSB research paper was the easy part — the harder part was designing it so a brand-new user does not feel lost the moment they land on it, and so it does not just repeat what Quickstart or Docs would later say. Getting that separation right took real iteration.

**Quickstart.** Once Get Started was settled, Quickstart came together faster, with troubleshooting guidance built in from the start rather than added later, plus small touches like subtle arrow animations to guide the eye through the steps.

**Docs.** This is where content architecture really mattered. Early on, it was not clear why Tutorials should exist separately from Docs if both explained NS-3 and OMNeT++ setup. After refining the split, the structure now makes sense: installation lives in Get Started and Quickstart, deeper simulator setup moves to Tutorials, and Docs stays focused on reference material — configuration, architecture, and API details, with code blocks and an "On This Page" sidebar for easy navigation. Font choice even got its own small saga: we tried Monaspace Argon for code blocks, then decided the original font actually worked better and reverted.

## A Deployment Bug Worth Mentioning

Not everything went smoothly. While preparing for deployment, the site kept failing to build — and the cause turned out to be a stray protobuf reference sitting in the root `.env` file. A small, easy-to-miss thing, but a good reminder that deployment issues are rarely where you expect them to be. Once fixed, the site deployed cleanly and Home and About were properly separated.

## Where Things Stand at Midterm

By the midterm evaluation, the Home, Get Started, and Quickstart pages were complete, the Docs section had its introduction and configuration content in place, and the site was live and deployed. The architecture diagram is currently being refined further with Hari, with ideas to make the app and simulator boxes and their connectors even clearer.

## What's Next

The second half of the project is focused on:

- Completing the **API reference section** in Docs
- Finalizing the **architecture diagram** on the About page
- Building out the **Tutorials** section (Beginner, Intermediate with NetworkX, Advanced with NS-3/OMNeT++)
- Adding the **Contribute** and **Community** sections
- Running usability validation to measure real time-to-first-success against the 15-minute target

Thank you for following along, and check out the live site at **[nsb-ucsc.github.io/nsb](https://nsb-ucsc.github.io/nsb/)** — I would love to hear what you think! Stay tuned for the final blog, where I will share how it all comes together.

If you would like to connect, find me on [LinkedIn](https://www.linkedin.com/in/avantika-pandey-4430512b4) or [GitHub](https://github.com/avantika1036).