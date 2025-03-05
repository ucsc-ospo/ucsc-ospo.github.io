---
title: "CarbonCast: Building an end-to-end consumption-based Carbon Intensity Forecasting service"
authors: [abelpc]
author_notes: ["Assistant Professor, University of California Santa Cruz"]
tags: ["osre25", "uc", "sustainability", "energy"]
date: 2025-02-18
lastmod: 2025-02-18
---

[CarbonCast](https://github.com/carbonfirst/carboncast) is a machine-learning-based approach to provide multi-day forecasts of the electrical grid's carbon intensity. Developed in Python, the current version of CarbonCast delivers accurate forecasts in numerous regions by using historical source production data of a particular geographical region, time of day/year, and weather forecasts as features. However, there is no easy way to access and visualize the data through a standard interface. In addition, much important information is left out and is not available to users. For instance, electricity grids often import electricity from neighboring regions and so electricity consumption depends on both electricity generation and imports. Moreover, it is imperative for each energy source to utilize a tailored predictive mechanism. Consequently, any carbon optimization solution trying to reduce carbon emissions due to its electricity consumption will benefit more from following a consumption-based CI signal. 

The plan for this project is to develop both the frontend and the backend API services for CarbonCast. We also intend to enhance CarbonCast by implementing an architecture wherein each region can employ a distinct interface for their predictive modeling. In scenarios where these new models do not yield superior outcomes within a region, the current architecture will serve as a fallback solution.


### Building an end-to-end consumption-based Carbon Intensity Forecasting service

- **Topics:** `Databases` `Machine Learning`
- **Skills:** Python, command line (bash), MySQL, Django, machine learning, cronjob
- **Difficulty:** Moderate
- **Size:** Medium (175 hours)
- **Mentors:** {{% mention "abelpc" %}}

Develop a containerized end-to-end backend, API, and frontend for collecting, estimating, and visualizing real-time and forecast electrical grid's carbon intensity data in a scalable manner.

Tasks:
- Research web technologies and frameworks relevant to CarbonCast development.
- Run and collect CarbonCast's data (CSV)
- Ingest CSV into a MySQL or SQLite database
- Develop an Application Programming Interface (API) and a Web User Interface (UI) to provide real-time data access and visualization. 
- Deploy the CarbonCast API as a service and dockerize it so that other users and applications can locally deploy and use it easily. 
- Implement a choropleth web map to visualize the carbon intensity data across the different geographical regions supported by CarbonCast.
- Enhance CarbonCast by implementing an extensible architecture wherein every region can employ distinct models for their predictive modeling. 


