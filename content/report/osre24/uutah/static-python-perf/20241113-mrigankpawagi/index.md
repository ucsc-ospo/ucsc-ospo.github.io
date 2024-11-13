---
title: "Final Report: Deriving Realistic Performance Benchmarks for Python Interpreters"
# subtitle: "YOUR SUBTITLE (OPTIONAL)"
summary:
authors: [mrigankpawagi]
#   - USERNAME1
#   - USERNAME2
tags: ["osre24", reproducibility, python, "performance benchmarks", "load testing"]
categories: []
date: 2024-11-12
lastmod: 2024-11-12
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
# image:
#   caption: "..."
#   focal_point: "Center"
#   preview_only: false
---
Hi, I am Mrigank. As a _Summer of Reproducibility 2024_ fellow, I have been working on [deriving realistic performance benchmarks for Python interpreters](/report/osre24/uutah/static-python-perf/20240817-mrigankpawagi/) with {{% mention bennn %}} from the University of Utah. In particular, we want to benchmark Meta's Static Python interpreter (which is a part of their Cinder project) and compare its performance with CPython on different levels of typing. In this post, I will share updates on my work since my [last update](https://ucsc-ospo.github.io/report/osre24/uutah/static-python-perf/20240909-mrigankpawagi/). This post forms my final report for the _Summer of Reproducibility 2024_.

## Since Last Time: Typing Django Files

Based on the profiling results from load testing a Wagtail blog site, I identified three modules in Django that were performance bottlenecks and added shallow types to them. These are available on our GitHub repository.

1. [`django.db.backends.sqlite3._functions`](https://github.com/utahplt/static-python-perf/blob/main/Benchmark/django/shallow/db/backends/sqlite3/_functions.py)
2. [`django.utils.functional`](https://github.com/utahplt/static-python-perf/blob/main/Benchmark/django/shallow/utils/functional.py)
3. [`django.views.debug`](https://github.com/utahplt/static-python-perf/blob/main/Benchmark/django/shallow/views/debug.py)

I also wrote a [script](https://github.com/utahplt/static-python-perf/tree/main/Tool_shed/driver) to mix untyped, shallow-typed, and advanced-typed versions of a Python module and create a series of such _gradually typed_ versions.

## Summary of Experience and Contributions

1. I tried to set up different versions of Zulip to make them work with Static Python. My setup scripts are available in our [repository](https://github.com/utahplt/static-python-perf/tree/main/Benchmark/zulip). Unfortunately, Zulip's Zerver did not run with Static Python due to incompatibility of some Django modules. A few non-Django modules were also initially throwing errors when run with Static Python due to a [bug in Cinder](https://github.com/facebookincubator/cinder/issues/137) – but I was able to get around with a hack (which I have described in the linked GitHub issue I opened on Cinder's repository).

2. I created a _locust-version_ of the small Django-related benchmarks available in [pyperperformance](https://github.com/python/pyperformance) and [skybison](https://github.com/facebookarchive/skybison). This helped me confirm that Django is by itself compatible with Static Python, and helped me get started with Locust. This too is available in our [repository](https://github.com/utahplt/static-python-perf/tree/main/Benchmark/django_sample).

3. As described in the midterm report, I created a complete pipeline with Locust to simulate real-world load on a Wagtail blog site. The instructions and scripts for running these load tests as well as profiling the Django codebase are available (like everything else!) in our [repository](https://github.com/utahplt/static-python-perf/tree/main/Benchmark/wagtail).

4. We added shallow types to the three Django modules mentioned above, and I created scripts to mix untyped, shallow-typed, and advanced-typed versions of a Python module to create a series of _gradually typed_ versions to be tested for performance. We found that advanced-typed code may often be structurally incompatible with shallow-typed code and are looking for a solution for this. We are tracking some examples of this in a [GitHub issue](https://github.com/utahplt/static-python-perf/issues/16).

## Going Forward

I had a great time exploring Static Python, typing in Python, load testing, and all other aspects of this project. I was also fortunate to have a helpful mentor along with other amazing team members in the group. During this project, we hit several roadblocks like the challenges in setting up real-world applications with Static Python and the difficulty in adding _advanced_ types – but are managing to work around them. I will be continuing to work on this project until we have a complete set of benchmarks and a comprehensive report on the performance of Static Python. 

Our work will continue to be open-sourced and available on our [GitHub repository](https://github.com/utahplt/static-python-perf) for anyone interested in following along or contributing.
