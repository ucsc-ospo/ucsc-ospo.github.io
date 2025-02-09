---
title: LLMSeqRec: LLM Enhanced Contextual Sequential Recommender
authors: ["Linsey Pang",bindong]
author_notes: ["Salesforce","Research Scientist, Lawrence Berkeley Lab"]
tags: ["osre25", "uc", "AI", "LLM", "Recommender"]
date: 2025-02-06T10:15:56-07:00
lastmod: 2025-02-06T10:15:56-07:00
---

###  Project Description
Sequential Recommender Systems are widely used in scientific and business applications to analyze and predict patterns over time. In biology and ecology, they help track species behavior by suggesting related research on migration patterns and environmental changes. Medical applications include personalized treatment recommendations based on patient history and predicting disease progression. In physics and engineering, these systems optimize experimental setups by suggesting relevant past experiments or simulations. Environmental and climate science applications include forecasting climate trends and recommending datasets for monitoring deforestation or pollution. In business and e-commerce, sequential recommenders enhance user experiences by predicting consumer behavior, suggesting personalized products, and optimizing marketing strategies based on browsing and purchase history. By leveraging sequential dependencies, these recommender systems enhance research efficiency, knowledge discovery, and business decision-making across various domains. Traditional sequential recommendation systems rely on historical user interactions to predict future preferences, but they often struggle with capturing complex contextual dependencies and adapting to dynamic user behaviors. Existing models primarily use predefined embeddings and handcrafted features, limiting their ability to generalize across diverse recommendation scenarios. To address these challenges, we propose LLM Enhanced Contextual Sequential Recommender (LLMSeqRec), which leverages Large Language Models (LLMs) to enrich sequential recommendations with deep contextual understanding and adaptive reasoning.
By integrating LLM-generated embeddings and contextual representations, LLMSeqRec enhances user intent modeling, cold-start recommendations, and long-range dependencies in sequential data. Unlike traditional models that rely solely on structured interaction logs, LLMSeqRec dynamically interprets and augments sequences with semantic context, leading to more accurate and personalized recommendations. This fusion of LLM intelligence with sequential modeling enables a more scalable, adaptable, and explainable recommender system, bridging the gap between traditional sequence-based approaches and advanced AI-driven recommendations. 



### Project Objectives
Aligned with the vision of the 2025 Open Source Research Experience (OSRE), this project aims to develop an open-source algorithm for multiple-object re-identification across diverse open-source data streams. As highlighted earlier, this method is expected to have wide-ranging applications in both scientific research and industry. Utilizing an open-source dataset, our focus will be on re-identifying common objects such as vehicles and pedestrians. The primary challenge lies in designing a unified algorithm, ReIDMM, capable of performing robust multi-object re-identification across multiple streams. Users will be able to tag any object as a target in a video or image for tracking across streams. Below is an outline of the algorithms to be developed in this project: 

- **Step 1: Target Object Identification**: Randomly select a target object from an image or video using object detection models such as YOLOv7. These models detect objects by generating bounding boxes around them. Target objects could include vehicles, pedestrians, animals, or other recognizable entities. This step ensures an initial object of interest is chosen for re-identification.

- **Step 2: Feature Extraction and Embedding**: Once the target object is identified, extract relevant features such as bounding box coordinates, timestamp, location metadata (if available), and visual characteristics. A multimodal embedding approach is used, where these features are transformed into a numerical representation (embedding vector) that captures the object's unique identity. This allows for efficient comparison across different images or videos.

- **Step 3: Searching and Matching**: To find the target object in other images or videos: (1) Extract embeddings of all objects detected in the other images/videos; (2) Compute similarity between the target object’s embedding and those of all detected objects using metrics like cosine similarity or Euclidean distance. (3) Rank objects by similarity, returning the most probable matches. The highest-ranked results are likely to be the same object observed from different angles, lighting conditions, or time frames.


### Project Deliverables
This project will deliver three things, software, evaluation results and demo. The software which implements the above ReIDMM algorithm will be hosted on the github repo as open-access repositories. The evaluation results and demo will be published along the github repo.


### ReIDMM

- **Topics**: ReIDMM: Re-identifying Multiple Objects across Multiple Streams`
- **Skills**: Proficient in Python, Experience with images processing, machine learning
- **Difficulty**: Difficult
- **Size**: Large (400 hours)
- **Mentor**: {{% mention bindong %}}, "Linsey Pang"



