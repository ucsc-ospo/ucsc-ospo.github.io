---
title: "Midterm Blog Measuring Open-source Database Systems under TPC-C Benchmark with Unreported Settings"
subtitle: ""
summary: "The project plans to understand the impact of missing settings on performance of the target open-source database systems."
authors: [ren.450]
author_notes: ["PhD Student at The Ohio State University"]
tags: ["osre23", reproducibility]
categories: [SoR'23]
date: 2023-08-02
lastmod: 2023-08-23
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

As part of the [Measuring Research Prototypes under Unreported Settings](/project/osre23/osu/missingsettings) my [proposal](https://drive.google.com/file/d/1ouFre-qMDCL_LiH5jFNUCOI1yAYHdWcS/view?usp=sharing) under the mentorship of {{% mention wang.7564 %}} and {{% mention yu.3053 %}} aims to understand the impact of missing settings in artifact evaluation. 

Based on our project proposal, the first step is to test the benchmark application on targeted systems. We pick open-source database system PostgreSQL as the target system. We test the TPC-C benchmark on PostgreSQL under default settings. We measure the throughput performanace for the benchmark by setting scalefactor as 10 and incrementing worker terminals. The settings for database server are all default values. We will take these results as baseline. In order to test on more parameters and system settings, we need to choose an association of parameters to get optimal throughput. 

We use an online tool [PGTune](https://pgtune.leopard.in.ua/#/), which aims to tune PostgreSQL config by the hardware. We select shared_buffer, min/max_wal_size and effective_cache_size as first set of parameters to measure. They are related to memory consumption, checkpoints and planner cost in the database server. Based on PostgreSQL [official documentation](https://www.postgresql.org/docs/current/runtime-config.html), shared_buffer sets the amount of memory the database server uses for shared memory buffers. Max_wal_size sets the maximum size to let the WAL grow during automatic checkpoints. Larger settings for shared_buffers usually require a corresponding increase in max_wal_size, in order to spread out the process of writing large quantities of new or changed data over a longer period of time. Effective_cache_size sets the planner's assumption about the effective size of the disk cache that is available to a single query. This is factored into estimates of the cost of using an index; a higher value makes it more likely index scans will be used, a lower value makes it more likely sequential scans will be used. 

We conduct the experiments by setting the parameters with increments and compare the throughput performance with each other and the baseline. Based on the results, the throughput of the benchmark with larger shared_buffer and max_wal_size is up to 1.5X of the performance under default settings. The improvement by tuning max_wal_size is larger than that of tuning shared_buffer. The increased effective_cache_size does not have effect for this benchmark workload compared to its default value of the system.

There are more values of above mentioned parameters to test. Next, I will test those parameters with increments of the values. Furthemore, we need to choose an association of more parameters to get optimal throughput. Also, the tuning tool may not generate optimal values for very high memory systems based on its description. This requires we test more possible parameters and their values for better performance.
