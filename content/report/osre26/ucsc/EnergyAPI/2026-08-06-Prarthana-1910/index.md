---
title: "My GSoC 2026 Midterm Update: Building the Foundation for EnergyAPI"
subtitle: "From understanding CarbonCast to designing a provider-agnostic API for carbon-aware scheduling"
summary: "Midterm update for my Google Summer of Code 2026 project with UC OSPO, covering CarbonCast, EnergyAPI, regional forecasting models, and the initial implementation of JobAPI and TemporalAPI."
authors:
  - prarthana-patil
tags: ["osre26", "gsoc26", "energyapi", "carboncast", "machine-learning", "open-source"]
categories: ["GSoC 2026", "EnergyAPI"]
date: 2026-08-06
lastmod: 2026-08-06
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "Smart"
  preview_only: false
---

Hello everyone!

It's been a little over two months since I started my Google Summer of Code journey with the **UC Open Source Program Office (UC OSPO)**. My project focuses on integrating **CarbonCast** with **EnergyAPI**, a system that uses carbon intensity and electricity forecasts to recommend when (and eventually where) electrical loads should run with lower environmental impact.

When I started, I expected to spend most of my time building APIs. Instead, the first half of GSoC was spent understanding a fairly large research codebase and preparing the infrastructure needed before any meaningful development could begin.

The first milestone was getting the entire CarbonCast repository running locally. From there, I traced the complete forecasting pipeline, from weather data acquisition and preprocessing to feature generation, model training, and carbon intensity forecasting. Understanding how these pieces fit together gave me the context needed to start contributing instead of treating the project as a black box.

Another major part of the project involved preparing the training data. CarbonCast relies on weather forecasts for multiple electricity grid regions, so I downloaded, processed, and organized hundreds of gigabytes of weather data spanning United States of America and Europe. Once the data pipeline was ready, I began training regional forecasting models and have currently initiated training for around 40 regions while validating the workflow and outputs.

{{< figure src="feature.png">}}

Alongside the forecasting work, I worked closely with my mentor, **Abel Souza**, on designing the architecture of EnergyAPI.

The goal of EnergyAPI is not to produce forecasts itself, but to provide a common interface that can consume information from different providers such as CarbonCast, Electricity Maps, WattTime, or other forecasting methods and turn those forecasts into practical scheduling recommendations. By separating the forecasting layer from the decision-making layer, the same scheduling logic can work regardless of where the underlying energy data comes from.

To support this, the API is divided into independent modules. **ProviderAPI** manages the available data providers and forecasting methods, **JobAPI** describes the characteristics and flexibility of different electrical loads, while **TemporalAPI** recommends the best execution windows for those jobs using forecasted energy and carbon metrics. Future work will extend this further through **SpatialAPI**, allowing recommendations across multiple regions in addition to time.

As part of the implementation, I have started developing the **JobAPI** and **TemporalAPI** modules using **FastAPI**.

One of the interesting aspects of JobAPI is that it models the flexibility of electrical loads instead of treating every job the same. For example, a dishwasher can usually be delayed but cannot be interrupted once it starts, whereas an EV charging session or an AI inference workload may be interruptible, power-scalable, or even migratable to another region. Representing these constraints allows the scheduler to generate recommendations that are both practical and carbon-aware.

Building on that, TemporalAPI focuses on the question: **"When should this job run?"** Given a forecast window and a job's flexibility constraints, it ranks candidate execution windows and recommends schedules that reduce expected carbon emissions. For interruptible workloads, the API can also recommend segmented execution while respecting limits such as maximum interruptions and minimum run durations.

Looking back, the first half of GSoC has been more about building a strong foundation than producing visible features. Understanding an existing research project, preparing large-scale datasets, training forecasting models, designing an extensible API, and beginning its implementation have all been essential steps before integrating everything into a complete system.

Over the next few weeks, my focus will be on completing the remaining regional model training, expanding the EnergyAPI implementation, integrating the trained CarbonCast models with the API, and validating the complete scheduling pipeline end to end.

Finally, I'd like to thank my mentor, **Abel Souza**, and the entire **UC OSPO** community for their guidance and continuous feedback throughout the project. I'm looking forward to sharing the complete system in my final GSoC report.
