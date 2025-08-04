---
title: "Midterm Report: Learning, Building, and Documenting Brahma"
subtitle: ""
summary: "Shaping Brahma’s first release by building routing, documentation, and immersive WebXR example systems."
authors: 
  - kajalJotwani
tags: ["osre25", "uc", "VR", "webXR"]
categories: ["open source", "virtual reality", "web development"]
date: 2025-08-05
lastmod: 2025-08-05
featured: true
draft: false

---

## Project Overview

**Brahma-XR** is an open-source WebXR framework designed for building collaborative virtual environments especially those involving spatial data and scientific visualization.

What makes Brahma powerful is that the same codebase runs seamlessly across both the browser and XR devices like the Apple Vision Pro, Meta Quest 3, and VARJO. This makes it ideal for rapid prototyping and creating cross-platform immersive experiences.

Some of Brahma’s built-in features include:
- Grab-and-pull locomotion  
- Raycasting and interaction  
- Avatar embodiment  
- Spatial rendering  
- Support for geospatial and data-driven visualizations  

Brahma is intentionally lightweight, optimized to run even on low-compute devices—making immersive collaboration more accessible to everyone.



## What Worked (and What Didn’t)

As Brahma transitioned from a private research repo to a public open-source project, a lot of important foundational work had to be done around documentation, packaging, and example previews.

There are two aspects that make Brahma especially unique:
1. **Bipartite npm package structure** – which requires detailed and thoughtful documentation.
2. **Immersive, real-time examples** – unlike typical libraries, Brahma’s examples aren’t just static demos. They are live, multi-user XR apps designed to be interacted with.

The first half of the project focused on setting the stage—structuring and preparing the framework for broader use.

### 🔧 Key Accomplishments

- **Learning Three.js**  
  I spent time learning the fundamentals of Three.js—how it handles 3D rendering, scene setup, materials, cameras, and animations. I also explored how large-scale Three.js projects are organized, which helped me understand how Brahma’s example apps are built.

- **Setting up the project structure**  
  I looked at the architecture of various open-source projects and used that knowledge to shape Brahma’s structure. The goal was to align with community best practices while keeping things clean and modular for future contributors.

- **Understanding npm packaging (especially bipartite)**  
  Since Brahma includes both client- and server-side logic, I spent time understanding how multi-part npm packages are published and maintained. I explored best practices around versioning, distribution, and separating internal vs public modules.

- **Creating a documentation system**  
  After exploring different approaches (and with my mentor’s help), I set up a static documentation site using [JSDoc](https://jsdoc.app/) with the Docdash theme. The current version includes guides, API references, and contribution instructions. This is just the beginning—the docs will evolve as the community grows.

## What’s Next

In the second half of the project, I’ll be focusing on:

- **Building a routing system**  
  For both documentation and example apps, so that users can easily browse through different components and use cases.

- **Setting up UI and 3D infrastructure**  
  To make it easier for others to start building apps with Brahma by providing clean base layers for interface and spatial development.

- **Prepping for the first public release**  
    Publishing the Brahma NPM package along with a curated set of featured examples and contributor-friendly documentation—making it easier for developers to get started and contribute.

## Reflection

This project has truly been the highlight of my summer. Learning about WebXR, Three.js, and open-source workflows has been both exciting and rewarding. Every challenge taught me something new.

I am specially greatfull to my mentor **Samir Ghosh** for his constant support, patience, and guidance. It’s been a privilege learning from you!

I'm looking forward to what’s coming next as we get closer to the first public release of Brahma!
