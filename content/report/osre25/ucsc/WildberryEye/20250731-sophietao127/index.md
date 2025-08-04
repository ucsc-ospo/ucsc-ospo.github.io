---
title: "Midterm Blog - WildBerryEye User Interface"
subtitle: 
summary:
authors: 
  - sophietao127
tags: ["osre25", "wildberryeye", "RaspberryPI5"]
categories: ["osre25", "Embedded Software"]
date: 2025-07-16
lastmod: 2025-07-31
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

Hi, my name is Sophie Tao, I am an alumn at the University of Washington, with majoring in Electrical and Computer Engineering,
I’m happy to share the progress I have been able to make over the last six weeks on my GSoC 2025 project, WildBerryEye, mentored by [Carlos Isaac Espinosa](/content/authors/caiespin).

# Project Overview
WildBerryEye is an open-source initiative to support ecological monitoring of pollinators such as bees and hummingbirds using edge computing and computer vision. The project leverages a Raspberry Pi and YOLO for object detection and aims to provide an accessible, responsive, and real-time web interface for researchers, ecologists, and citizen scientists.

This project specifically focuses on building the frontend and backend infrastructure for WildBerryEye’s user interface, enabling:

- Real-time pollinator detection preview
  - Real-time image capture
  - Real time video capture
- Responsive, User-friendly UI
- Object detection 
- Researcher-friendly configuration and usability

# Progress So Far
✅ Phase 1: Setup
- Frontend: Completed React + TypeScript project initialization with routing and base components. Pages include:
  - Home page (with image preview)
  - Dashboard page (pollinator image & video)

- Backend: Flask server initialized with modular structure. Basic API endpoints stubbed as per the proposal.

✅ Phase 2: Core Features
- Real-Time Communication:
Frontend successfully receives image stream using WebSocket.

- UI Components:
  - Implemented image carousel preview on homepage.
  - Image Capture (Image download)
  - Video Capture (Video Preview, Video Recording)
  - Sidebar-based navigation and page structure fully integrated.

- API Development:
  - Implemented core endpoints such as /home, and/dashboard routes.
  - Backend handlers structured for image and video capture.


# Challenges Encountered
⚠️ Real-time Image Testing: Lack of consistent live camera input made local testing inconsistent. \
⚠️ Allocate the camera module for both capture image and capture video. \
⚠️ Obtain the proper format of the video.

# Next Steps
- Enable more features for video capture
- Integrated with Machine Learning Model
- Conduct at least one usability test (self + external user) and incorporate feedback.
- Final Testing & Docs

# Summary
At this midterm stage, the WildBerryEye UI project is on track with core milestones completed, including real-time communication, component setup, and backend API structure. The remaining work focuses on refinement, visualizations, testing, and documentation to ensure a polished final product by the end of GSoC 2025.
