---
title: "EnergyAPI: An End-to-End API for Energy-Aware Forecasting and Scheduling"
authors: [abelpc]
author_notes: ["Assistant Professor, University of California Santa Cruz"]
tags: ["osre26", "uc", "electricity", "sustainability", "cloud", "evs"]
date: 2026-01-30
lastmod: 2026-01-30
---

Over the past decades, electricity demand has increased steadily, driven by structural shifts such as the electrification of transportation and, more recently, the rapid expansion of artificial intelligence (AI). Power grids have responded by expanding generation capacity, integrating renewable energy sources such as solar and wind, and deploying demand-response mechanisms. However, the current pace of demand growth is increasingly outstripping grid expansion, leading to integration delays, greater reliance on behind-the-meter consumption, and rising operational complexity.

To mitigate the environmental and socioeconomic impacts of electricity consumption, large consumers such as cloud data centers and electric vehicle (EV) charging infrastructures are increasingly participating in demand-response programs. These programs provide consumers with grid signals indicating favorable periods for electricity usage, such as when energy is cheapest or has the lowest carbon intensity. Consumers can then shift workloads across time and location to better align with grid conditions and their own operational constraints. A key challenge, however, is the online nature of this problem: operators must make real-time decisions without full knowledge of future grid conditions. While forecasting and optimization techniques exist, their effectiveness depends heavily on workload characteristics, such as whether tasks are delay-tolerant cloud jobs or EV charging sessions with route and deadline constraints.

This project proposes the design and implementation of a modular, extensible API for energy-aware workload scheduling. The API will ingest grid signals alongside workload Service Level Objectives (SLOs) and operational requirements, and produce execution plans that adapt to changing grid conditions. It will support multiple pluggable scheduling strategies and heuristics, enabling developers to compare real-time and forecast-based approaches across different workload classes. By providing a reusable, open-source interface for demand-response-aware scheduling, this project aims to lower the barrier for developers to integrate energy-aware decision-making into distributed systems and applications.


### Building an End-to-End Service for Energy Forecasting and Scheduling

- **Topics:** `Databases` `Machine Learning`
- **Skills:** Python, command line tools (bash), SQL (MySQL or SQLite), FastAPI, time-series analysis, basic machine learning
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "abelpc" %}}

Develop a containerized, end-to-end platform consisting of a backend, API, and web-based frontend for collecting, estimating, and visualizing real-time and forecasted electrical grid signals. These signals include electricity demand, prices, energy production, grid saturation, and carbon intensity. The system will support scalable data ingestion, region-specific forecasting models, and interactive visualizations to enable energy-aware application development and analysis.

Tasks:
- Study electrical grid signals and demand-response data sources (e.g., demand, price, carbon intensity, grid saturation) and identify their requirements for real-time and forecast-based consumption planning.
- Design and implement a relational data model for storing historical, real-time, and forecasted grid signals.
- Ingest and validate grid signal data into a MySQL or SQLite database, ensuring data quality and time alignment across regions.
- Implement baseline time-series forecasting models for grid signals (e.g., demand, price, or carbon intensity), with support for region-specific configurations.
- Query European Network of Transmission System Operators for Electricity (ENTSO-E) and EIA (Energy Information Administration (EIA)) APIs to collect grid data.
- Develop a RESTful API that exposes both raw and forecasted grid signals for use by energy-aware applications and schedulers.
- Build a web-based user interface to visualize historical trends, forecasts, and regional differences in grid conditions.
- Implement an interactive choropleth map to display spatial variations in grid signals such as carbon intensity and electricity prices.
- Design an extensible architecture that allows different regions to plug in custom forecasting models or heuristics.
- Containerize the backend, API, and frontend components using Docker to enable reproducible deployment and easy integration by external users.


