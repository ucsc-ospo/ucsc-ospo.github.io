---
title: "LMS Toolkit: Final Thoughts and Retrospect"
subtitle: ""
summary:
authors:
  - jkelman
tags: ["osre26", "gsoc", "lms-toolkit", "CLI", "python", "lms"]
categories: ["GSoC 2026", "LMS-Toolkit"]
date: 2026-09-01
lastmod: 2026-09-01
featured: true
draft: false
image:
  focal_point: "Center"
  preview_only: false
---
In my [GSoC Project Proposal](https://summerofcode.withgoogle.com/proposals/details/PTHkQi17), I set out to expand the [LINQS Lab's](https://linqs.org) [LMS-Toolkit](/project/osre26/ucsc/lms-toolkit) functionality to support [Moodle](https://moodle.org/).
I was eager to begin my open-source journey and excited to use my programming skills to contribute to a production software system.
Despite my ambition, there were many unforeseen obstacles that hindered my progress.
I would inevitably encounter hurdles such as Moodle's confusing database schema and handling Moodle's "Edit Mode" appropriately.
Nevertheless, I was eventually able to overcome these hardships and complete the Moodle utilities to load and list courses, course users, and course assignments.
Moreover, I developed an html-cleaning utility to provide fine-tuned cleaning of stored test data responses across all supported [LMSs](https://en.wikipedia.org/wiki/Learning_management_system).
Furthermore, I intend to continue my development, beginning with improved testing infrastructure by making a loading option configurable.
I feel I have accomplished my goal of increasing the LMS-Toolkit's capabilities by developing some of the primary tools for Moodle.

In retrospect, there are a few things I wish I could have told myself before I started this project that also may be helpful for future contributors.
At times, I would get frustrated when progress would slow or halt.
This is an unavoidable part of the learning process and is not a reflection of your lack of ability.
Similarly, mistakes are to be expected as a junior developer.
The important response is to acknowledge them, learn from them, and avoid repeating them.

It cannot be overstated how much I have grown as a developer throughout this project.
Docker, Python-specific conventions, HTTP requests, proper code documentation, CI, compiled and interpreted languages, and git are just a handful of the concepts I am much more familiar with now.
Additionally, I am grateful for all of the meetings my mentor, [Eriq Augustine](/author/eriq-augustine)
He was not only helpful with my tasks related to the project; we would also often discuss related general programming topics and he was able to make quite complex technical concepts easy for me to understand.
I also valued an environment where I could make mistakes, learn from them, and grow without fear of repercussions.
Although I am still in the early stages of my programming journey, I am significantly more confident in my programming skills thanks to this opportunity [UCSC OSPO](https://ucsc-ospo.github.io/) has provided me.

Previous blog posts:
    - [LMS Toolkit: Expanding Support for Moodle](/report/osre26/ucsc/lms-toolkit/20260613-jkelman/)
    - [LMS Toolkit: Listing Assignments in Moodle](/report/osre26/ucsc/lms-toolkit/20260722-jkelman/)
