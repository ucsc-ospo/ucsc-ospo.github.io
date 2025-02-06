---
title: "ReIDMM: Re-identifying Multiple Objects across Multiple Streams"
authors: [bindong, "Linsey Pang"]
author_notes: ["Research Scientist, Lawrence Berkeley Lab", "Salesforce"]
tags: ["osre25", "uc", "AI", "Image Processing", "Search"]
date: 2025-02-06T10:15:56-07:00
lastmod: 2025-02-06T10:15:56-07:00
---

###  Project Description
Re-identifying multiple objects across multiple streams (ReIDMM) is essential in scientific research and various industries. It involves tracking and analyzing entities across different viewpoints or time frames. In astronomy, ReIDMM helps track celestial objects like asteroids and space debris using multiple observatories. In biology and ecology, it enables the identification of animals across different camera traps and aids in tracking microscopic organisms in laboratory studies. In physics and engineering, it is used for tracking particles in high-energy physics experiments, monitoring structural changes in materials, and identifying robots or drones in lab automation. Beyond scientific applications, ReIDMM plays a critical role in industries such as retail, where it tracks customer behavior across multiple stores and improves sales and prevents theft. In smart cities, it supports traffic monitoring by identifying vehicles across intersections for improved traffic flow management. In manufacturing, it enables supply chain tracking by locating packages across conveyor belts and warehouse cameras. In autonomous systems, ReIDMM enhances multi-camera sensor fusion and warehouse robotics by identifying pedestrians, obstacles, and objects across different camera views.


### Project Objectives
Aligned with the vision of the 2025 Open Source Research Experience (OSRE), this project aims to develop an open-source algorithm for multiple-object re-identification across diverse open-source data streams. As highlighted earlier, this method is expected to have wide-ranging applications in both scientific research and industry. Utilizing an open-source dataset, our focus will be on re-identifying common objects such as vehicles and pedestrians. The primary challenge lies in designing a unified algorithm, ReIDMM, capable of performing robust multi-object re-identification across multiple streams. Users will be able to tag any object as a target in a video or image for tracking across streams. Below is an outline of the algorithms to be developed in this project: 

- **Step 1: Target Object Identification**: Randomly select a target object from an image or video using object detection models such as YOLOv7. These models detect objects by generating bounding boxes around them. Target objects could include vehicles, pedestrians, animals, or other recognizable entities. This step ensures an initial object of interest is chosen for re-identification.

- **Step 2: Feature Extraction and Embedding**: Once the target object is identified, extract relevant features such as bounding box coordinates, timestamp, location metadata (if available), and visual characteristics. A multimodal embedding approach is used, where these features are transformed into a numerical representation (embedding vector) that captures the object's unique identity. This allows for efficient comparison across different images or videos.

- **Step 3: Searching and Matching**: To find the target object in other images or videos: (1) Extract embeddings of all objects detected in the other images/videos; (2) Compute similarity between the target object’s embedding and those of all detected objects using metrics like cosine similarity or Euclidean distance. (3) Rank objects by similarity, returning the most probable matches. The highest-ranked results are likely to be the same object observed from different angles, lighting conditions, or time frames.


### Project Deliverables
This project will deliver three things, software, evaluation results and demo. The software which implements the above ReIDM2 algorithm will be hosted on the github repo as open-access repositories. The evaluation results and demo will be published along the github repo.


### ReIDMM

- **Topics**: ReIDMM: Re-identifying Multiple Objects across Multiple Streams`
- **Skills**: Proficient in Python, Experience with images processing, machine learning
- **Difficulty**: Difficult
- **Size**: Large (350 hours)
- **Mentor**: {{% mention bindong %}}, "Linsey Pang"



