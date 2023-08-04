---
title: "PDC Midterm Evaluation"
subtitle: ""
summary: ""
authors: [nijwang]
author_notes: ["UCSC Student"]
tags: ["osre23", "uc"]
categories: ["database"]
date: 2023-07-30
lastmod: 2023-07-30
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

## Mid-Term Evaluation Update

Hello! I'm Nick, a GSoC contributor for the Proactive Data Containers (PDC) Project. 
Over the past few weeks I've worked on verifying the functionality of the Python API for the PDC project and ensuring the smooth onboarding for new users of the data containers.

I began by documenting the installation of the Ubuntu virtual machine in order to run the PDC repository, since the project wasn't initially supported on Apple silicon hardware. The installation notes that I recorded for PDC would help contribute towards a more refined and precise process that can be seen updated on the github webpage.

After installing the dependencies of the project onto the VM, I would begin maintaining the existing Python API and making changes that would allow the tests to compile and run successfully. The manual setup had a few problems with file directories paths that prevented the installation of a few files on new devices, which I fixed by manually by linking the path and removing a few header files. However, this proved to only be a temporary fix as the prior issues was evidence of a hardcoded path, which was resolved by some alteration and fishing in the source code.

Now the PDC and PDCpy installations should go smoothly regardless of what OS is being used, and the instruction documentation can be found from the github page which should allow any user to access the data containers.