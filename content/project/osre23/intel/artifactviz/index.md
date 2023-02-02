---
title: "Public Artifact Data and Visualization"
authors: ["Anjo Vahldiek-Oberwagner"]
author_notes: ["Research Scientist at Intel Labs"]
tags: ["osre23", "reproducibility"]
date: 2023-01-09T10:15:56-07:00
lastmod: 2023-01-09T10:15:56-07:00
---

Reproducibility and Artifact Evaluation efforts have focused on reproducing the results, but not necessarily on storing, visualizing and making the results accessible. This set of projects builds the initial building blocks to log, capture, and visualize experiments.

### Experiment Log

- **Topics:** Provide tools to log experiments
- **Difficulty:** Simple
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** [Anjo Vahldiek-Oberwagner](mailto:anjovahldiek@gmail.com)

Develop a client and server side tool to start/stop an experiment, timestamp the experiment. Document each iteration of the experiment and create a database to visualize the log of experiments.

### Capture HW/SW state & continuous monitoring

- **Topics:** Record initial state
- **Difficulty:** Medium
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** [Anjo Vahldiek-Oberwagner](mailto:anjovahldiek@gmail.com)

Provide simple tools to gather the initial state of each experimental machine and its connected devices, configurations, software versions, ... Upload into the experiment log database and visualize the recorded data. Ideally, provide diff function between experimental runs.  

In a second step, monitor the machine’s state during the execution. This includes, network, memory, CPU, general OS statistics.  

### Record and visualize experimental results

- **Topics:** Record results in various formats and visualize them
- **Difficulty:** Hard
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** [Anjo Vahldiek-Oberwagner](mailto:anjovahldiek@gmail.com)

Description: Experiments generate results in various formats (e.g., CSV, json, text files, …). The goal of this project is to provide tools to extract common formats, connect the results to the experiment log and visualize them. Ideally, allowing to compare different experimental runs. Initially, the project could dump their results into a Prometheus instance (https://prometheus.io/) which would later become available for everyone to explore the data.
