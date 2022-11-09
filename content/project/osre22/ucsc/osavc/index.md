---
title: "Open Source Autonomous Vehicle Controller"
authors: ["Aaron Hunter"]
author_notes: ["Ph.D. Student, UC Santa Cruz"]
tags: ["osre22", "uc", "autonomous vehicles"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

The OSAVC is a vehicle-agnostic open source hardware and software project.  This project is designed to provide a real-time hardware controller adaptable to any vehicle type, suitable for aerial, terrestrial, marine, or extraterrestrial vehicles. It allows control researchers to develop state estimation algorithms, sensor calibration algorithms, and vehicle control models in a modular fashion such that once the hardware set has been developed switching algorithms requires only modifying one C function and recompiling.

Lead mentor: [Aaron Hunter](mailto:aamuhunt@ucsc.edu)

Projects for the OSAVC:


### Vehicle/Craft sensor driver development
 - **Topics**: Driver code to integrate sensor to a microcontroller
 - **Skills**: C, I2C, SPI, UART interfaces
 - **Size** 175 hours
 - **Difficulty** Medium
 - **Mentor** Aaron Hunter


Help develop a sensor library for use in autonomnous vehicles.  Possible sensors include range finders, ping sensors, IMUs, GPS receivers, RC receivers, barometers, air speed sensors, etc. Code will be written in C using state machine methodology and non-blocking algorithms. Test the drivers on a Microchip microncontroller.


### Path finding algorithm using OpenCV and machine learning
 - **Topics**: Computer vision, blob detection
 - **Skills**: C/Python, OpenCV
 - **Size** 175 or 350 hours 
 - **Difficulty** Medium
 - **Mentor** Aaron Hunter


Use OpenCV to identify a track for an autonomous vehicle to follow.  Build on previous work by developing a new model using EfficientDet and an existing training set of images. Port the model to TFlite and implement on the Coral USB Accelerator. Evaluate its performance against our previous efforts. 


### State estimation/sensor fusion algorithm development
 - **Topics**: Kalman filtering, Mahoney
 - **Skills**: C/Python, Matlab/Simulink, numerical optimization algorithms
 - **Size** 350 hours
 - **Difficulty** Challenging
 - **Mentor** Aaron Hunter


Implement an optimal state estimation algorithm from a model.  This model can be derived from a Kalman filter or some other state estimation filter (e.g., Mahoney filter).  THe model takes sensor readings as input and provides an estimate of the state of a vehicle. Finally, convert the model to standard C using the Simulink code generation or implement in Python (for use on a single board computer, e.g., Raspberry Pi)
