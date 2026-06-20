---
title: "Environmental NeTworked Sensor I: Customizable Dashboard, Layouts, Equations, Export, and Registry"
subtitle: "Introducing my GSoC 2026 project with UC OSPO"
summary: "Making the ENTS (DirtViz) dashboard easier to grow with real field use through dynamic sensor catalogs, drag-and-drop layouts, and performance improvements."
authors:
  - Mehbub_10
tags: ["osre26", "gsoc", "ents", "data-visualization", "react", "flask", "postgresql"]
categories: ["GSoC 2026", "ENTS"]
date: 2026-06-19
lastmod: 2026-06-19
featured: true
draft: false

image:
  caption: "DirtViz dashboard with customizable chart panels"
  focal_point: "Center"
  preview_only: false
---

Hi! I'm **Mehbub**, an indie hacker and full stack engineer from India ([GitHub](https://github.com/devleo10)). I'm a **Google Summer of Code 2026** contributor with **UC OSPO**, working on the [Environmental NeTworked Sensor (ENTS)](/project/osre26/ucsc/ents) project under {{% mention "cjosephson" %}}, [John Madden](mailto:jtmadden@ucsc.edu), and [Alec Levy](mailto:alevy1@ucsc.edu). You can read my full [proposal here](https://drive.google.com/file/d/1Zi8G1u9xBfSHJ71oPjFmsbd_PaWYnzVI/view?usp=sharing).

[ENTS](https://github.com/jlab-sensing/ENTS-backend) — also known as **DirtViz** — is an open sensing platform for monitoring microbial fuel cell sensors and other environmental measurements in the field. You can see it live at [dirtviz.jlab.ucsc.edu](https://dirtviz.jlab.ucsc.edu/).

## What I'm building (and why)

The short version: I want the ENTS dashboard to feel like something researchers can actually *use* day to day, not something that only works when the frontend happens to match the database.

Right now, a lot of the dashboard is still stitched together by hand in React. That gets painful fast when new sensors show up, or when someone wants a different layout for the same cell data.

My main goal is to let the app **discover what can be plotted** from live database information — mostly from the `sensor` table — instead of keeping long static chart lists in the frontend. The UI should ask the backend what a cell actually has, then build panels from that answer.

Power and TEROS data may still live on older paths for a while, so the catalog needs a clear bridge between those legacy sources and the newer sensor model.

The feature I'm most excited about is a **drag-and-drop dashboard**: reorder panels, add or remove them, and keep the layout in the **URL** so you can share a view with a link. Server-side saved layouts can come later — first I want the client-side behavior to be solid and predictable.

For people comparing **multiple cells**, I also want loads to feel snappier: fetch in parallel where it makes sense, and ignore stale responses when someone changes cells or dates before the previous request finishes.

After that foundation, I'll move on to **equations for derived metrics** (with strict server-side validation) and **CSV export** of what's already on screen.

This is incremental work on the existing **Flask + React** stack, not a rewrite. I'm trying to keep current APIs stable unless there's a clear reason to extend them.

## Tech stack

**Python**, **JavaScript**, **React**, **Flask**, and **PostgreSQL** — the same stack ENTS already uses.

I'll share progress updates as the summer goes on. Stay tuned!
