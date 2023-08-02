---
title: "Midterm: Open Source Autonomous Vehicle Controller"
subtitle: ""
summary: ""
authors: [25ChilingH]
author_notes: ["Student at The Harker School, San Jose"]
tags: ["osre23"]
categories: []
date: 2023-08-01
lastmod: 2023-08-01
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

As part of the [Open Source Autonomous Vehicle Controller Project](/project/osre23/ucsc/OSAVC) my [proposal](https://docs.google.com/document/d/1hDU87aAzbn88vWwOHH0ggIID2W4KKzp8SKF1Lb8LU90/edit?usp=sharing) under the mentorship of **Aaron Hunter and Carlos Espinosa** aimed to create comprehensive technical documentation to help onboard new users of the OSAVC controller.

I have accomplished the following:
* From the KiCad Schematic Editor, created pinouts of the I/O connectors on the OSAVC.
* Detailed a hardware overview of the OSAVC by labeling and describing each electrical component. 
* Documented the setup for loading code on the OSAVC, including software such as Git, MPLAB X, XC32 Compiler, and serial terminal and hardware by showing how to connect the PICKit3 and OSAVC to a PC.
* Tested the OSAVC by receiving and transmitting characters in the serial port into a buffer.
* Fixed bugs/errors in the NEO_M8N GPS module library and PWM motors library.
* Created a new library for the uni and bidirectional ESC brushless motors.
* Created a user-interfaced test harness for all peripherals: serial, IMU, GPS, encoder, PWM actuators, radio telemetry, Mavlink heartbeat, radio controller, and LIDAR.
* Incorporated new user interface element and fixed video streaming errors in the Flask app running on the Raspberry Pi 4 communicating with the OSAVC.
* Documented both software and hardware steps to run the OSAVC with a companion computer such as a Raspberry Pi 4.
* Highlighted common problems encountered with the OSAVC.
* Created a contributor's guide for others to create new libraries or contribute to the OSAVC project.
* Designed a [switching voltage regulator](https://grabcad.com/library/ptn78020w-1) in SOLIDWORKS
* Designed a self balancing bot that employs the OSAVC in SOLIDWORKS

## Future Work
Currently, the laser cutter at UCSC is in maintenance, so we couldn't assemble the self balancing bot yet. Once we assemble it, I will finish and document the control algorithms. We can also try incorporating ML models on the Raspberry Pi with the Coral USB accelerator on the self balancing bot.
