---
title: "Enhancing Usability and Expandability of the Open Sensing Platform project"
subtitle: "Open Sensing Platform (OSP)"
summary: 
authors: [ahmedfalah01]
tags: ["osre24"]
categories: ["GSoC'24"]
date: 2024-06-14
lastmod: 2024-06-14
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: "TopLeft"
  preview_only: false
---
Greetings everyone,

I am Ahmed Falah and I am delighted to be part of the 2024 Google Summer of Code program, where I am contributing to the [Open Sensing Platform project](/project/osre24/ucsc/osp).

My [proposal](https://drive.google.com/file/d/1jD2BvRBaCHfiibEcR5sJKr9GWK51RxD7/view?usp=sharing) was accepted, and I am fortunate to have {{% mention cjosephson %}} and [John Madden](mailto:jtmadden@ucsc.edu) as my mentors. The objective of my project is to enhance usability and expandability of the Open Sensing Platform, a hardware solution for deploying sensor networks in outdoor environments. This platform utilizes low-power, long-range communication to transmit data from various sensors to a visualization dashboard. While the platform effectively collects data, its configuration process requires modifying source code to make it more user-friendly. My first steps to enhance usability of the project:

- **Improve User Interface (UI):** Develop a user-friendly interface to interact with the platform, enabling researchers to configure the device without modifying code.
- **Conversion of user configuration:** convert user configuration data to the Protobuf format for efficient storage and transmission.

Additionally, I will explore updating the NVRAM functions to interact with Protobuf messages instead of directly writing/reading raw data to NVRAM. I will also implement functions to serialize user configuration data into a Protobuf message and deserialize the message back into a data structure for use within the firmware.

I will be posting regular updates and informative blogs throughout the summer, so stay tuned!
