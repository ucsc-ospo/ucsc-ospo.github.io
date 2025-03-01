---
title: "ReasonWorld"
authors: [profjamesdavis]
author_notes: ["Professor CSE, UC Santa Cruz"]
tags: ["osre25", "UC", "reproducibility", "AR/VR", "Multimodal", "World model", "LLM/VLM"]
date: 2025-02-28
lastmod: 2022-02-28
---

### ReasonWorld: Real-World Reasoning with a Long-Term World Model

A world model is essentially an internal representation of an environment that an AI system would construct based on external information to plan, reason, and interpret its surroundings. It stores the system’s understanding of relevant objects, spatial relationships, and/or states in the environment. Recent augmented reality (AR) and wearable technologies like Meta Aria glasses provide an opportunity to gather rich information from the real world in the form of vision, audio, and spatial data. Along with this, large language (LLM), vision language models (VLMs), and general machine learning algorithms have enabled nuanced understanding and processing of multimodal inputs that can label, summarize, and analyze experiences. 

With **ReasonWorld**, we aim to utilize these technologies to enable advanced reasoning about important objects/events/spaces in real-world environments in a structured manner. With the help of wearable AR technology, the system would be able to capture real-world multimodal data. We aim to utilize this information to create a long-memory modeling toolkit that would support features like:
- Longitudinal and structured data logging: Capture and storing of multimodal data (image, video, audio, location coordinates etc.)
- Semantic summarization: Automatic scene labeling via LLMs/VLMs to identify key elements in the surroundings
- Efficient retrieval: For querying and revisiting past experiences and answering questions like “Where have I seen this painting before?”
- Adaptability: Continuously refining and understanding the environment and/or relationships between objects/locations.
- Adaptive memory prioritization: Where the pipeline can assess the contextual significance of the captured data and retrieve those that are the most significant. The model retains meaningful, structured representations rather than raw, unfiltered data.

This real-world reasoning framework with a long-term world model can function as a structured search engine for important objects and spaces, enabling:
- Recognizing and tracking significant objects, locations, and events
- Supporting spatial understanding and contextual analysis
- Facilitating structured documentation of environments and changes over time

### Alignment with Summer of Reproducibility:
- Core pipeline for AR data ingestion, event segmentation, summarization, and indexing (knowledge graph or vector database) would be made open-source.
- Clear documentation of each module and how they collaborate with one another
- The project could be tested with standardized datasets, simulated environments as well as controlled real-world scenarios, promoting reproducibility
- Opportunities for Innovation - A transparent, modular approach invites a broad community to propose novel expansions


### Specific Tasks:
- A pipeline for real-time/batch ingestion of data with the wearable AR device and cleaning
- Have an event segmentation module to classify whether the current object/event is contextually significant, filtering out the less relevant observations.
- Have VLMs/LLMs summarize the events with the vision/audio/location data to be stored and retrieved later by structured data structures like knowledge graph, vector databases etc.
- Storage optimization with prioritizing important objects and spaces, optimizing storage based on contextual significance and frequency of access.
- Implement key information retrieval mechanisms
- Ensure reproducibility by providing datasets and scripts

### ReasonWorld
- **Topics:** `Augmented reality` `Multimodal learning` `Computer vision for AR` `LLM/VLM` `Efficient data indexing`
- **Skills:** Machine Learning and AI, Augmented Reality and Hardware integration, Data Engineering & Storage Optimization
- **Difficulty:** Hard
- **Size:** Large (350 hours)
- **Mentors:** [James Davis](mailto:davisje@ucsc.edu), [Alex Pang](mailto:pang@soe.ucsc.edu)

