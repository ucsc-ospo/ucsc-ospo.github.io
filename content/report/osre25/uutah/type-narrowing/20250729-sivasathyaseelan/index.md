---
title: "Type Narrowing: Evaluate New Gradual Languages and Do Unsound Narrowings Lead to Exploits"
# subtitle: "YOUR SUBTITLE (OPTIONAL)"
summary:
authors: [sivasathyaseelan]
#   - USERNAME1
#   - USERNAME2
tags: ["osre25", reproducibility, Type Narrowing, Software Security, Programming Languages]
categories: []
date: 2025-07-29
lastmod: 2025-07-29
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
# image:
#   caption: ""
#   focal_point: ""
#   preview_only: false
---

Hello! I’m Siva Sathyaseelan D N, a pre-final year B.Tech + M.Tech Engineering student at IIT BHU, Varanasi, India. With a deep-rooted passion for software development and scientific computing. I thrive at the intersection of code and real-world problem-solving. For two years, I’ve engaged in open-source work across scientific simulation, blockchain, and cloud-native technologies, through hobby projects, hackathons, internships, and an LFX mentee. I'm contributing to[Type Narrowing: Evaluate New Gradual Languages and Do Unsound Narrowings Lead to Exploits](/project/osre25/uutah/type-narrowing/) under the mentorship of [Ben Greenman](/content/authors/bennn). My proposal can be viewed [here](https://docs.google.com/document/d/1QcfiOWQQBxTW3YnkCmgfz-xHwLGad4OuCMjyphbaz54/edit?usp=sharing)!

## Project Overview

Gradual typing enhances untyped languages like JavaScript and Python with static type checkers in systems like TypeScript, Flow, Mypy, Pyright, and Typed Racket, using type narrowing to refine types via runtime checks (e.g., typeof item["price"] === "number"). Designs vary, TypeScript permits unverified predicates, Flow ensures soundness, and Typed Racket tracks types compositionally—prompting the If-T benchmark [ift-benchmark](https://github.com/utahplt/ift-benchmark) to evaluate narrowing across five languages, though it omits tools like Sorbet, Hack, Luau, Pyre, Cinder/Static Python, Typed Clojure, and Elixir, and the risks of unsound narrowings remain unclear.

**Objectives**
- Extend the If-T benchmark to Sorbet, Hack, Luau, Pyre, Cinder/Static Python, Typed Clojure, and potentially Elixir.
- Analyze their type narrowing precision, expressiveness, and soundness.
- Conduct a corpus study of TypeScript or Python code using GitHub or Software Heritage APIs.
- Assess the prevalence and exploit potential of unsound narrowings.
- Link corpus findings to benchmark results for broader insights.

## Progress So Far

During the first half of the SoR 2025 period, I focused on lextending the If-T benchmark to Sorbet, Pyre, Cinder/Static Python, Typed Clojure. These are the PRs which extends If-T benchmark:
- Sorbet -> https://github.com/utahplt/ifT-benchmark/pull/20
- Pyre -> https://github.com/utahplt/ifT-benchmark/pull/26
- Typed Clojure -> https://github.com/utahplt/ifT-benchmark/pull/27
- Cinder -> https://github.com/utahplt/ifT-benchmark/pull/28

## What's Next

I will be working on Conduct a corpus study of TypeScript or Python code using GitHub or Software Heritage APIs. Assess the prevalence and exploit potential of unsound narrowings. Also Link corpus findings to benchmark results for broader insights [TGUsage](https://github.com/utahplt/TGUsage).

## Final Thoughts

Working on **Type Narrowing** has been incredibly rewarding, it’s more than just code. It’s studying the type systems of different programming languages which is very important for the large scale software systems and softwware security, and I’m honored to be a part of that.

Big thanks to my mentors **Ben Greenman** for their support and thoughtful feedback throughout. I’ve learned a ton already, and I can’t wait to keep building.