---
title: "Open Source Autonomous Vehicle Controller"
authors: ["Aaron Hunter"]
author_notes: ["UC Santa Cruz Researcher"]
tags: ["osre23", "uc", "autonomous vehicles","robotics"]
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
 - **Mentor** [Aaron Hunter](mailto:aamuhunt@ucsc.edu), [Carlos Espinosa](mailto:caiespin@ucsc.edu), Pavlo Vlastos


Help develop sensor libraries for use in autonomous vehicles. We are in particular interested in sensors for UAVs: airspeed sensors (pitot tube) or barometers, but also proximity detectors (ultrasonic), and range sensors. Code will be written in C using state machine methodology and non-blocking algorithms. Test the drivers on a Microchip microncontroller.


### Technical Documentation
 - **Topics**: Documentation
 - **Skills**: Technical writing, markdown language, website
 - **Size** 175 hours 
 - **Difficulty** Medium
 - **Mentor** Aaron Hunter/Carlos Espinosa/Pavlo Vlastos


Technical Documentation:
Write a tutorial to demonstrate how to start with an OSAVC and program it with the robotic equivalent of HelloWorld, moving onto more sophisticated applications. Create a web page interface to the OSAVC repo highlighting this tutorial. In this project you will start from scratch with an OSAVC PCB and bring it to life, while documenting it in a way to help new users.

### ROS/Gazebo Robot Simulation
 - **Topics**: Robot simulation with ROS/Gazebo
 - **Skills** ROS/Gazebo, Python
 - **Size** 175 or 350 hours 
 - **Difficulty** Medium to Hard
 - **Mentor** [Aaron Hunter](mailto:aamuhunt@ucsc.edu), [Carlos Espinosa](mailto:caiespin@ucsc.edu), Pavlo Vlastos

Generate a simulated world and a quadcopter model in ROS/Gazebo. Provide a link from Mavlink to ROS using the mavros package and simulate a real vehicle data stream to command the simulated quadcopter in Gazebo. At the same time return the image stream from Gazebo to allow for offline processing of ML models on the images. 

