---
title: "Midterm Check-In: Progress on the AutoAppendix Project"
authors: [kkrassni]
tags: ["osre24", "sc24", "chameleon", "reproducibility"]
categories: [SoR]
date: 2024-08-03
lastmod: 2024-08-03
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

# Midterm Check-In: Progress on the AutoAppendix Project

Hi all,

I'm happy to share a quick update on the AutoAppendix project as we’re about
halfway through. We’ve made some steady progress on evaluating artifacts from SC24 papers, and we're starting
to think about how we can use what we've learned to
improve the artifact evaluation process in the future.

## What We’ve Been Up To

As a quick reminder, the goal of our project is to develop a set of guidelines that
researchers can use to improve the reproducibility of their work. We're focusing
on papers from the Supercomputing Conference 2024 that applied for an "Artifact Replicable" badge, and we're
evaluating their artifacts to see how well the experiments can be replicated. As it was difficult to make assumptions about the exact outcomes of the project besides detailed experiment recreation, our main goal of this
midterm check-in is to share what insights we have gathered so far and to set the stage for the final outcomes.

Our main task so far has been making a selection of submissions with experiments designed
for Chameleon Cloud, or those that could be easily adapted to run on Chameleon. As there were 45 submissions that applied
for an "Artifact Replicable" badge, it was not easy
to choose which ones to evaluate, but we managed to narrow
it down to 18 papers that we thought would be a good fit for our project.

We've chosen to focus on papers that do not require
special hardware (like a specific supercomputer) or
complex network setups, as it would be difficult to
generalize the insights from these kinds of
experiments. Instead, we've been looking at those 
that require only a *single computation node*, and
could theoretically be run with the available hardware
on Chameleon.

## Observations and Learning Points

At the moment, we're about halfway through the
evaluation process. So far, we've noticed a range of
approaches to documenting and setting up computational
experiments. Even without looking at the appendices in
detail, it's clear that there’s a lot of room for
standardization of the documentation format and software setup, which could make life easier for
everyone involved. This particularly applies to
software setups, which are often daunting to replicate,
especially when there are specific version requirements, version
incompatibilities or outright missing dependencies. Since the main goal of this
project is to develop a set of guidelines that
researchers can use to improve the reproducibility of
their work, suggesting a way to deal with software
versions and dependencies will be a key part of our
results.

We’ve observed that submissions with well-structured and detailed appendices
tend to fare better in reproducibility checks. This includes those that utilized
containerization solutions like Docker, which encapsulate the computing
environment needed to run the experiments and thus
eliminates the need for installing specific software
packages. It’s these kinds of practices that we
think could be encouraged more broadly.

## Looking Ahead

The next steps are pretty exciting! We’re planning to use what we’ve learned to draft some
guidelines that could help future SC conference submissions be more consistent.
This might include templates or checklists that ensure all the necessary details
are covered.

Additionally, we’re thinking about ways to automate some parts of the artifact
evaluation process. The goal here is to make it less labor-intensive and more
objective. A particularly nice way 
of reproducible artifact evaluation is
Chameleon's JupyterHub interface, which in conglomeration with the *Trovi*
artifact sharing platform makes it easy to share artifacts and allow interested
parties to reproduce the experiments with minimal effort. We are thus looking into ways to
utilize and contribute to these tools in a way that could benefit the broader research community.

## Wrapping Up

That’s it for now! We are working towards getting
as many insights as possible from the rest of the
artifact evaluations, and hopefully, by the end of this project, we’ll have some solid
recommendations and tools to show for it. Thanks for keeping up with our
progress, and I’ll be back with more updates as we move into the final stages of
our work.