---
title: "WaDAR"
authors: [{{% mention "cjosephson" %}}, {{% mention "ericdvet" %}}]
author_notes: ["Assistant Professor, University of California Santa Cruz", "Graduate Student Researcher. University of California Santa Cruz]
tags: ["osre25", "uc", "wireless sensing", "agrotech"]
date: 2025-02-05
lastmod: 2025-02-05
---

[WaDAR](https://github.com/jlab-sensing/wadar) (Water Radar) is an innovative, low-cost, hybrid approach to soil moisture sensing that combines the benefits of in-ground (in situ) and remote sensing technologies. Traditional soil moisture measurement methods suffer from drawbacks: in situ sensors are expensive and difficult to maintain, while remote sensing offers lower accuracy and resolution. WaDAR bridges this gap by using inexpensive underground backscatter tags paired with above-ground radars, enabling completely wireless, high-resolution soil moisture monitoring.

## Key Features of WaDAR
- Uses **RF backscatter tags** buried underground to provide high-accuracy soil moisture readings.
- Uses **ultra-wideband radar** for above-ground sensing.
- Offers an average error of just 1.4%, comparable to state-of-the-art commercial sensors.
- Reduces deployment costs significantly, making it accessible for widespread agricultural use.
- Supports real-time, scalable, and maintenance-free soil moisture monitoring for farmers.

### Improving and Optimizing Data Processing Pipeline for More Accurate Soil Moisture Measurements

- **Topics:** `Digital Signal Processing` `Machine Learning`
- **Skills:** C/embedded, signal processing, machine learning, MATLAB (optional)
- **Difficulty:** Moderate
- **Size:** Medium (175 hours)
- **Mentors:** {{% mention "cjosephson" %}}, {{% mention "ericdvet" %}}

Enhance the accuracy of soil moisture measurements by refining the data processing pipeline.

Tasks:
- Develop and test algorithms for noise reduction and signal improvement.
- Implement advanced filtering and statistical techniques to improve measurement precision.
- Validate improvements using real-world field data.
- Translate algorithms into embedded to be implemented in real-time embedded hardware.  

### Improving Backscatter Tag PCB

- **Topics:** `Hardware Design` `Signal Processing`
- **Skills:** PCB design, RF knowledge
- **Difficulty:** Moderate
- **Size:** Medium (175 hours)
- **Mentors:** {{% mention "cjosephson" %}}, {{% mention "ericdvet" %}}

Enhance the performance of WaDAR's backscatter tags by optimizing PCB design for improved signal-to-noise ratio (SNR) and implementing a communication protocol for tag identification.

Tasks:
- Redesign PCB for improved readings.
- Implement and test a communication protocol to distinguish between multiple tags.
- Evaluate hardware changes in real-world field conditions.
- Optimize power consumption and scalability for practical deployment.