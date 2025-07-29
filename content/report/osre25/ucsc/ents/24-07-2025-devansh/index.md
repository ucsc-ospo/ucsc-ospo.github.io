---
title: "Midway Through GSoC: ENTS"
subtitle: "Building a Robust Sensor Data Visualization Platform"
summary: A midterm update on my GSoC 2025 project under OSRE. This post covers the motivation, goals, and current progress on improving the ENTS platform for large-scale environmental sensing.
authors:
  - devansh
tags: ["osre25", "gsoc2025", "data-visualization", "environmental-sensing"]
date: 2025-07-24
lastmod: 2025-07-24
featured: true
draft: false
---

# Midway Through GSoC

Hi everyone! I’m **Devansh Kukreja**, and I’m excited to share a midterm update on my [Google Summer of Code 2025 project](https://summerofcode.withgoogle.com/programs/2025/projects/OPlG0KHV) with the **University of California, Santa Cruz Open Source Program Office (UC OSPO)** under the **Open Source Research Experience (OSRE)**. I'm contributing to [**ENTS**](https://github.com/jlab-sensing/ENTS-backend), a platform that supports real-time monitoring and visualization of environmental sensor networks.

## Project Overview

The **Environmental NeTworked Sensor (ENTS)** platform is an open-source web portal designed to collect, visualize, and analyze data from distributed sensor networks. It’s used by researchers and citizen scientists to monitor field-deployed sensors measuring soil moisture, temperature, voltage, and current—supporting critical research on sustainability and environmental change.

My project focuses on improving the platform’s **stability, usability, and extensibility** through:

- Fixing bugs in the data visualization components.
- Enhancing real-time chart synchronization and data point selection.
- Improving overall system error handling and reliability.
- Building a **Logger Registration System** that enables users to register and configure their logging devices.
- Exploring integration with **The Things Network (TTN)** to support LoRaWAN-based wireless sensor connectivity.

## Progress So Far

During the first half of the GSoC period, I focused on laying the groundwork for a more robust and user-friendly system. Highlights include:

- **Enhanced date range logic:** Improved the way the dashboard selects time periods by automatically choosing a recent two-week window with valid sensor data. This ensures charts always display meaningful insights and avoids showing blank states.

- **Improved chart rendering:** Refined how charts behave when there's no data or when unusual values (like negatives) are present. This includes smoother axis alignment and fallback messaging when data is unavailable.

- **Refactored cell management UI:** Cleaned up and improved the modals used to manage cells and sensors, fixing several UI/UX issues and bugs to make interactions more intuitive and consistent.

- **Enabled smart URL syncing:** The dashboard state now stays in sync with the URL, making it easier to share specific views or navigate back to previous states without losing context.

## What's Next

In the second half of the program, I’ll be focusing on:

- Building out and polishing the **Logger Registration UI** based on the backend schema and wireframes.
- Finalizing the onboarding flow for field loggers, linking registration data to ingestion and dashboard views.
- Continuing work on LoRaWAN support with **TTN**, aiming to enable basic OTA provisioning for future deployments.
- Exploring an admin dashboard that helps visualize device health, sync status, and alert on any anomalies.

## Final Thoughts

Working on ENTS has been incredibly rewarding—it’s more than just code. It’s about making tools that help scientists and conservationists understand our changing environment, and I’m honored to be a part of that.

Big thanks to my mentors **Colleen Josephson**, **John Madden**, and **Alec Levy** for their support and thoughtful feedback throughout. I’ve learned a ton already, and I can’t wait to keep building.
