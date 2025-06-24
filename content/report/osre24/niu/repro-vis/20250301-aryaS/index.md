---
title: "Static and Interactive Visualization Capture"
subtitle: "Investigate Solutions for Capturing Visualizations"
summary: ""
authors: [aryaS]
author_notes: ["Founding Engineer @ Docunexus Inc."]
tags: ["osre24","data visualization","reproducibility"]
categories: [SoR'24]
date: 2024-08-30
lastmod: 2024-08-30
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

## Introduction
Hello! My name is {{% mention aryaS %}} a machine learning engineer and researcher based out of Kolkata, a city in Eastern India dubbed the City of Joy.
During summer of 2024, I worked closely with Professor {{% mention dakoop %}}  on the project titled [Reproducibility in Data Visualization](/project/osre24/niu/repro-vis/). 
We explored multiple existing solutions and tested different stratergies and made great progress in the capture of visualiations using a relatively less used method of embedding visualization meta-information into the final resultant visualizations jpg as a json object.

## Progress and Challenges

Static Visualization Capture

We successfully developed a method to capture static visualizations as .png files along with embedded metadata in a JSON format. 
This approach enables seamless reproducibility of the visualization by storing all necessary metadata within the image file itself. 
Our method supports both Matplotlib and Bokeh libraries and demonstrated near-perfect reproducibility, with only a minimal 1-2% pixel difference in cases where jitter (randomness) was involved.


Interactive Visualization Capture

For interactive visualizations, our focus shifted to capturing state changes in Plotly visualizations on the web. 
We developed a script that tracks user interactions (e.g., zoom, box, lasso, slider) using event listeners and automatically captures the visualization state as both image and metadata files. 
This script also maintains a history of interactions to ensure reproducibility of all interaction states.

The challenge of capturing web-based visualizations from platforms like ObservableHq remains, as iframe restrictions prevent direct access to SVG elements. 
Further exploration is needed to create a more robust capture method for these environments.

<p align="center">
  <img src="./bokeh_interactive.png" alt="bokeh interactive capture" style="width: 80%; height: auto;">
</p>

# Future Work

We aim to package our interactive capture script into a Google Chrome extension. 

Temporarily store interaction session files in the browser’s local storage.

Enable users to download captured files as a zip archive, using base64 encoding for images.

# Conclusion
The last summer, we made significant strides in enhancing data visualization reproducibility. 
Our innovative approach to embedding metadata directly into visualization files offers a streamlined method for recreating static visualizations. 
The progress in capturing interactive visualization states opens new possibilities for tackling a long-standing challenge in the field of reproducibility.


