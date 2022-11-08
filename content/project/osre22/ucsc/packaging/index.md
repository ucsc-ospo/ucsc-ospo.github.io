---
title: "Package Management & Reproducibility"
authors: ["Farid Zakaria"]
author_notes: ["Ph.D. Student, UC Santa Cruz"]
tags: ["osre22", "uc", "reproducibility"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

Project ideas related to reproducibility and package management, especially as it relates to _store type package managers_ ([NixOS](http://nixos.org/), [Guix](https://guix.gnu.org/) or [Spack](https://spack.io/)).

Lead Mentor: [Farid Zakaria](https://users.soe.ucsc.edu/~fmzakari) <mailto:fmzakari@ucsc.edu>
### Investigate the dynamic linking landscape

- **Topics:** `Operating Systems` `Compilers` `Linux` `Package Management` `NixOS`
- **Skills:** Experience with systems programming and Linux familiarity
- **Difficulty:** Moderate to Challenging
- **Size**: Large (350 hours)
- **Mentors:** [Farid Zakaria](mailto:fmzakari@ucsc.edu) & [Tom Scogland](https://people.llnl.gov/scogland1) <mailto:scogland1@llnl.gov>

Dynamic linking as specified in the ELF file format has gone unchallenged since it's invention. With many new package management models that eschew the filesystem hierarchy standard (i.e. Nix, Guix and Spack), many of the idiosyncrasies that define the way in which libraries are discovered are no longer useful and potentially harmful.

Specific tasks:
- Continue development on [Shrinkwrap](https://github.com/fzakaria/shrinkwrap) a tool to make dynamic library loading simpler and more robust.
- Evaluate it's effectiveness across a wide range of binaries.
- Upstream contributions to [NixOS](http://nixos.org/) or [Guix](https://guix.gnu.org/) to leverage the improvement when suitable.
- Investigate alternative improvements to dynamic linking by writing a dynamic linker "loadder wrapper" to explore new ideas.
