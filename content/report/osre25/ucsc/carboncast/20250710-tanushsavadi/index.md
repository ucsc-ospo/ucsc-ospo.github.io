---
title: "CarbonCast"
subtitle: "Expanding Real-Time Carbon Intensity Forecasting and Visualization"
summary: "A UCSC Open Source Research Experience (OSRE) project to build an API on top of CarbonCast, enabling individuals and organizations to access and act on real-time carbon intensity forecasts."
authors: 
  - tanushsavadi
tags: ["osre25", "uc", "carboncast"]
categories: ["web-development", "machine-learning", "api"]
date: 2025-07-10
lastmod: 2025-07-10
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

As part of the [CarbonCast project](/project/osre25/ucsc/carboncast), my [proposal](https://summerofcode.withgoogle.com/programs/2025/projects/7yvAix3k) under the mentorship of Professor Abel Souza aims to build an API that makes carbon intensity forecasts more accessible and actionable.

Under the mentorship of Professor Abel Souza, my proposal is centered around building upon CarbonCast to create an API to enable user access and utilization of energy data in optimizing their electricity consumption. Before diving into the details of the project, I’d like to share a bit about my background.

## About Me

Hi, I’m Tanush—a rising senior at the University of Massachusetts Amherst, majoring in Computer Science and Mathematics and graduating in Spring 2026. Currently, I’m an AI Intern for the Commonwealth of Massachusetts Department of Unemployment Assistance, where I’m developing an end-to-end retrieval-augmented generation (RAG) chatbot on AWS.

In the past, I’ve contributed to CarbonCast in a different capacity, designing a user interface to help visualize carbon intensity forecasts. I also worked at MathWorks as a Machine Learning Intern, where I collaborated in an AGILE environment to design and deploy predictive models that improved precision torque control and dynamic responsiveness in motor-driven robotic and industrial systems.

I’m excited to bring these experiences to this year’s GSoC project, where I’ll be building tools to make carbon data more accessible and actionable for everyone.

## What is CarbonCast?

CarbonCast is a Python-based machine-learning library designed to forecast the carbon intensity of electrical grids. Carbon intensity refers to the amount of carbon emitted per kilowatt-hour (kWh) of electricity consumed. Developed in Python, the current version of CarbonCast delivers accurate forecasts in numerous regions by using historical energy production data of a particular geographical region, time of day/year, and weather forecasts as features.

However, there is no easy way to access, visualize, and utilize the data through a standard interface. In addition, much important information is left out and is not available to users. For instance, electricity grids often import electricity from neighboring regions, and so electricity consumption depends on both electricity generation and imports. Moreover, it is imperative for each energy source to utilize a tailored predictive mechanism. Consequently, any carbon optimization solution trying to reduce carbon emissions due to its electricity consumption will benefit more from following a consumption-based carbon intensity signal.

Unlike other third-party carbon services, CarbonCast’s model is open-sourced, allowing users to study, understand, and improve its behavior. This transparency invites public collaboration and innovation. It also contrasts sharply with proprietary services that often withhold both the logic behind their models and the data they are trained on.

## Why This Matters

Electricity usage is one of the largest contributors to carbon emissions globally. Carbon intensity—the amount of carbon emitted per kilowatt-hour of electricity consumed—varies based on how electricity is generated and demanded (for example, coal versus solar). With better visibility into when the grid is cleaner, individuals and organizations can shift their energy consumption to lower-carbon periods and lower prices. This enables everyday energy optimizations without compromising comfort or productivity.

By improving CarbonCast’s accessibility and functionality, we are helping people and institutions answer questions like:

- When is the best time to charge my EV to reduce environmental impact?
- Can I run my energy-hungry server jobs when the electricity is cheaper?
- How do I actually reduce my emissions without guessing?

By providing clear, accurate forecasts of carbon intensity, CarbonCast can help users make informed decisions to optimize their energy footprint and reduce emissions without sacrificing convenience or productivity.

## What I’m Building

The plan for this summer is to develop the backend API services for CarbonCast. This summer, I’m focused on two major goals:

### Geographical Expansion

I am extending CarbonCast’s compatibility to support more regional electricity grids. Each model will be customized for local grid behavior and renewable energy characteristics. This involves tuning the model pipeline to adapt to each region’s energy mix, weather patterns, and reporting granularity.

### System Refactoring and Modularity

The original CarbonCast system was built as a research artifact. To refine it into production-grade infrastructure, I am refactoring the codebase to improve modularity. This makes it easier to plug in new regions, update forecasting algorithms, and integrate new data sources.

## Impact Beyond Research

The paper that inspired this project, *Multi-day Forecasting of Electric Grid Carbon Intensity using Machine Learning*, pioneered the idea of forecasting carbon intensity over multiple days using a hierarchical machine learning model. This goes beyond the typical 24-hour day-ahead models that are common in the industry and allows for better planning and longer-term decision-making.

CarbonCast builds directly on that foundation by transforming research into practical, real-world infrastructure. It is an open-source library that anyone can run, contribute to, and benefit from. Whether you're a developer building carbon-aware applications, a policymaker working on grid decarbonization strategies, or a sustainability-conscious individual looking to reduce your carbon footprint, CarbonCast provides the tools to make informed, impactful choices.

## Looking Ahead

I am excited to contribute to a project that blends machine learning, systems engineering, sustainability, and public impact. My goal is to help make it easier for everyone to see, understand, and act on their carbon footprint while also providing the "visibility" people need to take meaningful, informed actions.
