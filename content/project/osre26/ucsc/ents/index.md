---
title: "Environmental NeTworked Sensor (ENTS)"
authors: [cjosephson]
author_notes: ["UC Santa Cruz Assistant Professor"]
tags: ["osre26", "uc", "data visualization", "website design", "sensor development"]
date: 2026-01-30
lastmod: 2026-01-30
---

### ENTS I: Web portal for large-scale sensor networks

![Data Visualization Dashboard](osp1.png)
- **Topics:** Data Visualization, Backend, Frontend, UI/UX, Analytics
- **Skills:**
  - *Required:* React, Javascript, Python, SQL, Git
  - *Nice to have:* Flask, Docker, CI/CD, AWS, Authentication
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "cjosephson" %}}, [John Madden](mailto:jtmadden@ucsc.edu), [Alec Levy](mailto:alevy1@ucsc.edu)

The Environmental NeTworked Sensor (ENTS) platform, formally Open Sensing Platform (OSP), implements data visualization website for monitoring microbial fuel cell sensors (see [GitHub](https://github.com/jlab-sensing/DirtViz)). The mission is to scale up the current platform to support other researchers or citizen scientists in integrating their novel sensing hardware or microbial fuel cell sensors for monitoring and data analysis. Examples of the types of sensors currently deployed are sensors measuring soil moisture, temperature, current, and voltage in outdoor settings. The focus of the software half of the project involves building upon our existing visualization web platform, and adding additional features to support the mission. A live version of the website is available [here](https://dirtviz.jlab.ucsc.edu/).

Below is a list of project ideas that would be beneficial to the ENTS project. You are not limited to the following projects, and encourage new ideas that enhance the platform:
- Improve streaming functionality
- Generic interface for sensor measurements
- Logger registration
- Over the air (OTA) configuration updates
- Implement unit tests and API documentation

### ENTS II: Hardware to for large-scale field sensor networks

![Hardware](featured.png)
- **Topics:** Embedded system, wireless communication, low-power remote sensing
- **Skills:**
  - *Required:* C/C++, Git, Github, PlatformIO
  - *Nice to have:* STM32 HAL, ESP32 Arduino, protobuf, python, knowledge of standard communication protocols (I2C, SPI, and UART)
- **Difficulty:** Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "cjosephson" %}}, [John Madden](mailto:jtmadden@ucsc.edu), [Jack Lin](mailto:jlin143@ucsc.edu)

The Environmental NeTworked Sensor (ENTS) node aims to be a general purpose hardware platform for outdoor sensing (e.g. agriculture, ecological monitoring, etc.). The typical use case involves a sensor deployment in an agricultural field, remotely uploading measurements without interfering with farming operations. The current hardware revision ([Soil Power Sensor](https://github.com/jlab-sensing/soil_power_sensor) was originally designed for monitoring power output of microbial fuel cells using high fidelity voltage and current measurement channels, as well as auxiliary sensors such as the SDI-12 [TEROS-21 soil moisture sensor](https://metergroup.com/products/teros-21/). The primary activities of this project will involve low-level firmware design and implementation, but may also incorporate hardware design revisions if necessary. We are looking to expand functionality to other external sensors, as well as optimize for power consumption, via significant firmware design activities. 

Long-range, low-power wireless communication is achieved through a LoRa capable STM32 microcontroller with in-lab experiments using an ESP32 microcontroller to enable the simpler WiFi interface. Both wireless interfaces communicate upload measurements to our data visualization dashboard, **ENTS I**. The combined goal across both of these projects is to create a system that enables researchers to test and evaluate novel sensing solutions. We are looking to make the device usable to a wide range of researchers which may not have a background in electronics, so are interested in design activities that enhance user friendliness.

In total there will be 2-4 people working on the hardware with progress being tracked on GitHub. Broader project planning is tracked through a Jira board. We intend to have weekly meetings to provide updates on current issue progress along with assigning tasks. Please reach out to [John Madden](mailto:jtmadden@ucsc.edu) if there are any questions or specific ideas for the project.

Below is a list of project ideas that would be beneficial to the ENTS project. You are not limited to the following projects, and encourage new ideas that enhance the platform:
- Backup logging via SD card
- I2C multiplexing for multiple of the same sensors
- Batch sensor measurement uploading
