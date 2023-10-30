---
title: "Final Blog Measuring Open-source Database Systems under TPC-C Benchmark with Unreported Settings"
subtitle: ""
summary: "The project plans to understand the impact of missing settings on performance of the target open-source database systems."
authors: [ren.450]
author_notes: ["PhD Student at The Ohio State University"]
tags: ["osre23", reproducibility]
categories: [SoR'23]
date: 2023-10-25
lastmod: 2023-10-30
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

In my final blog, I will first introduce the project, then describe the achievements after the midterm and summarize our experiments. As part of the [Measuring Research Prototypes under Unreported Settings](/project/osre23/osu/missingsettings) my [proposal](https://drive.google.com/file/d/1ouFre-qMDCL_LiH5jFNUCOI1yAYHdWcS/view?usp=sharing) under the mentorship of {{% mention wang.7564 %}} and {{% mention yu.3053 %}} aims to understand the impact of missing settings in artifact evaluation. 

In my midterm blog(/report/osre23/osu/missingsettings/20230802-ren.450/), I took three paratmeters as the PostgreSQL config to test the performance of TPC-C benchmark and got some initial results about the effect of different parameters separately on throughput performance. After the midterm, I continue doing experiments on these four parameters (shared_buffer, min_wal_size, max_wal_size and effective_cache_size) with more values and associate them to measure the effect on performance. These parameters are related to memory consumption, checkpoints and planner cost in the database server. You can refer to my previous blog for details. 

For the experiment, we continue to measure the throughput performanace for the benchmark by setting scalefactor as 10 and incrementing worker terminals. The settings for database server are all default values except the four parameters we choose to tune. For the shared_buffer parameter, we choose from initial 128mb to 8gb, in total 6 values. Then for each shared_buffer setting, effective_cache_size includes three values, from initial 4gb to 16gb. Next, for each effective_cache_size setting we tune the min_wal_size and max_wal_size as a tuple, min_wal_size has two values and max_wal_size has four values, in total 6 values. We conduct the experiments by running three rounds for each setting and get all three throughput numbers and calculate their average values. 

Based on the [results](https://docs.google.com/spreadsheets/d/12OeSwZGq2G4-YGY5BTH5uZbVcAaxcZqYhqciCaBiF2E/edit?usp=sharing), the observation holds as the conclusion from midterm blog. The throughput of the benchmark  can be affected by tuning shared_buffer and max_wal_size. Effective_cache_size and min_wal_size do not have obvious effect for this benchmark. The improvement is limited after shared_buffer and max_wal_size reach a certain value.

In our experiment, we only choose three possible parameters for one benchmark. The experiment is expensive considering the consuming time. There are also more values of above mentioned parameters to test. This experiment can also indicate we may need to sample a subset of settings to generate observations that match those from a full extensive artifact evaluation.
