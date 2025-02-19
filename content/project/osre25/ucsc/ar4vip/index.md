---
title: "AR4VIP"
authors: ["alex pang"]
author_notes: ["CSE Professor, UC Santa Cruz"]
tags: ["osre25", "uc", "ar/vr", "navigation aid", "visually impaired people"]
date: 2025-02-18
lastmod: 2025-02-18
---

We are interested in developing navigation aids for visually impaired people (VIP) using AR/VR technologies.
Our intended use is primarily indoors or outdoors but within private confines e.g. person's backyard.
Using AR/VR headsets or smart glasses allows navigation without using a cane and frees
the users' hands for other tasks.

### Continue Development on Meta Quest 3 Headset

- **Topics:** `Dynamic scenes` `Spatial audio` `Proximity detection`
- **Skills:** AR/VR familiarity, WebXR, Unity, SLAM, good communicator, good documentation skills
- **Difficulty:** Moderate
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** [Alex Pang](mailto:pang@soe.ucsc.edu), [James Davis](davis@cs.ucsc.edu)

Continue development and field testing with the Meta Quest 3 headset.
See this [repository page](https://github.com/sail360/UCSC-VIP-Research) for current status.

Specific tasks:
- Improve spatial audio mapping
- Improve obstacle detection, at different heights, with pre-scanned geometry as well as dynamic objects
  e.g. other people, pets, doors
- Special handling of hazards e.g. stairs, uneven floors, etc.
- Explore/incorporate AI to help identify objects in the scene when requested by user

### New Development on Smart Glasses

- **Topics:** `Dynamic scenes` `Spatial audio` `Proximity detection`
- **Skills:** AR/VR familiarity, WebXR, Unity, SLAM, good communicator, good documentation skills
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** [Alex Pang](mailto:pang@soe.ucsc.edu), [James Davis](mailto:davis@cs.ucsc.edu)

VR headsets are bulky and awkward, but currently is more advanced than AR glasses in terms of programmability.
Ultimately, the form factor of smart glasses is more practical for extended use by our target users.
There are many vendors working on pushing out their version of smart glasses targetting various applications
e.g. alternative for watching TV, etc.  We are interested in those that provide capabilities to support
spatial computing.  Most of these will likely have their own brand specific APIs.  This project has 2 goals:
(a) develop generic brand-independent API, perhaps extensions to WebXR, to support overarching goal of navigation
aid for VIP, and 
(b) port functionality of VR version to smart glasses while taking advantage of smart glass functionalities and sensors.

Specific tasks:
- Explore current and soon-to-be-available smart glass options e.g. Snap Spectacles, Xreal Air 2 ultra, etc. and select a platform to work on (subject to cost and availability of SDK).  At a minimum, glass should be microphones and speakers, and cameras.  Infrared cameras or other low light capability is a plus.  Sufficient battery life or option for quick exchange.
- Identify support provided by SDK e.g. does it do realtime scene reconstruction? does it support spatial audio? etc.  If it supports features outside of WebXR, provide generic hooks to improve portability of code to other smart glasses.
- Port and extend functionalities from the Meta Quest 3 VR headsets to smart glass platform.
- Add AI support if glasses support them.
- Provide documentation of work.
