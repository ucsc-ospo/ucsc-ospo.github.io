---
title: "Apache AsterixDB"
authors: ["Ahmed Eldawy"]
author_notes: ["Professor of Computer Science, UC Riverside"]
tags: ["osre22", "uc"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[AsterixDB](http://asterixdb.apache.org/) is an open source parallel big-data management system. AsterixDB is a well-established Apache project that has beedddn active in research for more than 10 years. It provides a flexible data model that supports modern NoSQL applications with a powerful query processor that can scale to billions of records and terabytes of data. Users can interact with AsterixDB through a power and easy to use declarative query language, SQL++, which provides a rich set of data types including timestamps, time intervals, text, and geospatial, in addition to traditional numerical and Boolean data types.

### Geospatial Data Science on AsterixDB

- *Topics*: Data science, SQL++, documentation
- *Skills*: SQL, Writing, Spreadsheets
- *Difficulty*: Medium
- *Size*: Medium or Large (175 or 350 hours)
- *Mentors*: [Ahmed Eldawy](mailto:eldawy@ucr.edu), [Akil Sevim](mailto:asevi006@ucr.edu)

Build a data science project using AsterixDB that analyzes geospatial data among other dimensions. Use [Chicago Crimes](https://star.cs.ucr.edu/?Chicago%20Crimes#center=41.8313,-87.6830&zoom=11) as the main dataset and combine with other datasets including [points of interests](https://star.cs.ucr.edu/?osm21/pois#center=41.8313,-87.6830&zoom=11) [ZIP Code boundaries](https://star.cs.ucr.edu/?TIGER2018/ZCTA5#center=41.8313,-87.6830&zoom=11). During this project, we will answer interesting questions about the data and visualize the results such as:

- What is the most common crime type in a specific date or over the weekends?
- Where do most of the arrests happen?
- How are the crime rates change over time for different regions?

#### The goals of this project are:

- Understand how to build a scalable data science project using AsterixDB.
- Translate common questions to SQL queries and run them on large data.
- Learn how to visualize the results of queries and present them.
- Write detailed documentation about the process of building a data science application in AsterixDB.
- Improve the documentation of AsterixDB while working in the project to improve the experience for future users.

#### Machine Learning Integration
As a bonus task, and depending on the progress of the project, we can explore the integration of machine learning with AsterixDB through Python UDFs. We will utilize the AsterixDB Python integration through [user-defined functions](https://asterixdb.apache.org/docs/0.9.7/udf.html) to connect AsterixDB backend with [scikit-learn](https://scikit-learn.org/stable/index.html) to build some unsupervised and supervised models for the data. For example, we can cluster the crimes based on their location and other attributes to find interesting patterns or hotspots.
