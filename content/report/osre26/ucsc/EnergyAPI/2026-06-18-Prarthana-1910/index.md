---
title: "EnergyAPI: A Containerized, End-to-End Platform for Real-Time Grid
Signal Forecasting, Scheduling, and Visualization
"
subtitle: "Introduction of my GSoC 2026 project with UC OSPO"
summary: "Building the infrastructure behind EnergyAPI to transform real-time energy and weather data into actionable recommendations for sustainable and cost-effective workload scheduling.
"
authors:
  - Prarthana-1910
tags: ["osre26","gsoc","energyapi","energy-systems","carbon-aware-computing","react","docker"]
categories: ["GSoC 2026","EnergyAPI"]
date: 2026-06-18
lastmod: 2026-06-18
featured: true
draft: false

image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hello everyone! I’m Prarthana Patil, a third-year Electrical Engineering student at Nirma University. I am grateful for the opportunity to contribute to this project through Google Summer of Code 2026, as it closely aligns with my interests in energy systems, sustainability, and software engineering. I am excited to be working on this project under the mentorship of **Abel Souza**. A detailed overview of the project's goals, deliverables, and implementation roadmap is available in my accepted Google Summer of Code 2026 proposal: [Proposal Link](https://drive.google.com/file/d/1bLTX8uPQvOE0ZoTIky7J6DAZH_MqEN3O/view?usp=sharing).

In today’s world, the demand for electricity has increased significantly and at the same time, organizations are becoming more conscious of operational costs and sustainability goals. With the rapid growth of large scale data centres, AI workloads, cloud computing infrastructure, electric vehicles and high power consuming appliances like air conditioners and refrigerators leads to rise of tradeoff between sustainability and operational cost. 

EnergyAPI aims to bridge the existing gap by providing a unified platform for collecting, forecasting and presenting the real time grid information by a user friendly API. The platform uses in total five signals to arrive at a conclusion across various regions: carbon intensity, electricity demand, electricity price, energy generation mix and grid saturation. 

One of the most centralized concepts in this project is job. A job is a unit of electrical load that must be scheduled. Examples of jobs include AI model training, EV charging sessions, data processing tasks, etc. According to the nature of the job, the tradeoff between sustainability and cost occurs. The job depends on various factors like time of the day, location flexibility, weather/season, urgency, execution duration, deadline, and power requirements. By using the combination of these constraints with the forecasted grid conditions, the platform can recommend the best time and location to execute the job. A simple example can be seen in a smart laundry service. As customers, we generally care about when our clothes are ready rather than the exact moment the washing machine starts running. Suppose a washing machine load requires one hour to complete and can be executed anytime between 1 PM and 7 PM. The laundry service can define this workload as a job through EnergyAPI, and using forecasted information such as carbon intensity, electricity prices, and grid conditions, the platform can identify the most suitable one-hour window to execute the job while reducing both operational costs and carbon emissions.

During this project, I will be contributing to build an end-to-end pipeline that connects the real-time data acquisition, forecasting and scheduling. I will work on automating the collection of weather and grid data, storing and managing this information within a database, integrating forecasting models for key grid signals, and building scheduling mechanisms that produce optimized execution plans for incoming workloads. I will also work on extending the API layer and contributing to an interactive dashboard that enables users to visualize both historical and forecasted grid conditions.

Through EnergyAPI, I hope to contribute to building a platform that makes energy-aware and carbon-aware decision-making more accessible for developers, researchers, and organizations. Modern smart devices such as Apple Watch and other connected devices already have access to internet services and can retrieve carbon intensity information through APIs. By leveraging platforms like EnergyAPI, such devices can help users identify cleaner and more cost-effective times to schedule electricity-consuming activities. I am eager to learn from the community, collaborate, and contribute to a sustainable world.
