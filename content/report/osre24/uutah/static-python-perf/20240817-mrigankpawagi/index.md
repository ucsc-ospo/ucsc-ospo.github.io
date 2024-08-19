---
title: "Deriving Realistic Performance Benchmarks for Python Interpreters"
# subtitle: "YOUR SUBTITLE (OPTIONAL)"
summary:
authors: [mrigankpawagi]
#   - USERNAME1
#   - USERNAME2
tags: ["osre24", reproducibility, python, "performance benchmarks", "load testing"]
categories: []
date: 2024-08-17
lastmod: 2024-08-17
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Generated using Gemini"
  focal_point: "Center"
  preview_only: true
---
Hi, I am Mrigank. I am one of the _Summer of Reproducibility_ fellows for 2024, and I will be working on [deriving realistic performance benchmarks for Python interpreters](/project/osre24/uutah/static-python-perf/) with {{% mention bennn %}} from the University of Utah.

## Background and Motivation

Recent work by Meta on a statically typed variant of Python – Static Python – which has provided immense promise in moving towards gradually typed languages without compromising on performance due to lack of complete soundness. Lu et al.[^1] provide an evaluation of Static Python and conclude that the enhancement in performance reported by Meta on their web servers for Instagram is reasonable and is not just the result of refactoring. In fact, the study notes that very little refactoring is typically required for converting existing Python programs to Static Python. However, this study depends on a limited model of the language and does not represent real-world software applications.

In our project, we aim to create a realistic performance benchmark to reproduce performance improvements reported by Meta and to evaluate the performance of Static Python in real-world software applications. In addition, we will analyze partially-typed code to understand the performance implications of gradual typing in Python.

## Key Objectives

We will use widely-used open-sourced applications to derive realistic performance benchmarks for evaluating Static Python. In particular, we will focus on projects that utilize the Python framework [Django](https://www.djangoproject.com/), which is also known to power the backend of Instagram. We plan to begin with [Wagtail](https://github.com/wagtail/wagtail), a popular CMS built on Django. We have also identified other potential projects like [Zulip](https://github.com/zulip/zulip), [Plane](https://github.com/makeplane/plane) and [LibrePhotos](https://github.com/LibrePhotos/librephotos). These are all actively maintained projects with significantly large codebases.

Further, we will analyze the performance of partially-typed code. This will be of value to the Python community as it will provide confidence in gradually moving towards Static Python for improving performance. We will make our benchmarks publicly available for the community to use, reproduce, and extend.

## Methodology

### Load Testing

For each project that we derive benchmarks from, we will design user pipelines that simulate real-world usage and implement them to create load tests using the open-sourced [Locust](https://github.com/locustio/locust) framework. This will allow us to evaluate the performance of Static Python in real-world loads and scenarios. Locust can spawn thousands of users, each of which independently bombards the system with HTTP requests for a range of tasks that are defined in their user pipeline. We will host each project on a server (local or cloud) to run these load tests.

We will profile each project to ensure that our tests cover different parts of the codebase and to identify performance bottlenecks. We can then focus on these bottlenecks while gradually typing the codebase.

### Gradual Typing

For typing the code in these projects, we will create two versions of each project: one with the so-called "shallow" type annotations and another with "advanced" type annotations. The former is relatively easier to implement and we can use tools like [MonkeyType](https://github.com/Instagram/MonkeyType) to generate stubs that can be quickly verified manually. The latter is quite non-trivial and will require manual effort. We will then mix-and-match the three versions of each project to create different combinations of typed and untyped code. Note that this mix-and-match can be done at both the module level and also at the function or class level.

## Conclusion

This is my first time working on performance-benchmarking and I am excited to pick up new skills in the process. I am also looking forward to interacting with people from the Python community, people from Meta's Static Python team, and also with the maintainers of the projects we will be working on. I will be posting more updates on this project as we make progress. Stay tuned!

[^1]: Kuang-Chen Lu, Ben Greenman, Carl Meyer, Dino Viehland, Aniket Panse, and Shriram Krishnamurthi. Gradual soundness: Lessons from static python. _The Art, Science, and Engineering of Programming_.
