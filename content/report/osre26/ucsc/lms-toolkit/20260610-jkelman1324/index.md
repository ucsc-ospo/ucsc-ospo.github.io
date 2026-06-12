---
title: "LMS Toolkit: Expanding Support for Moodle"
subtitle: ""
summary:
authors:
  - jkelman1324
tags: ["osre26", "gsoc", "lms-toolkit", "CLI", "python", "lms"]
categories: ["GSoC 2026", "LMS-Toolkit"]
date: 2026-06-10
lastmod: YYYY-MM-DD
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

Hi! I am Jake Kelman, a Technology Project Manager for a company in the workers' compensation field. Most of my current work involves programming Google Apps Scripts to help automate department workflows and improve visibility of data via automated emails. Outside of my job, I have enjoyed developing applications such as an iOS word game and a Paigow Poker desktop game. Although these pet projects were fun and eductational, I am excited for the opportunity to further improve my skills and assist the open-source community. Through Google Summer of Code via UCSC OSPO, I will be contributing to the [LMS-Toolkit](/project/osre26/ucsc/lms-toolkit) project this summer!

The LMS-Toolkit includes a python interface with many different CLI tools used to interact with Learning Management Systems (LMSs) including Canvas, Moodle, and Blackboard. Examples of the LMS Toolkit's functionality include listing courses, course users (i.e. students and staff), gradebook, assignments and quizzes. All of these tools are fully accessible for the Canvas LMS, but there is minimal support for Moodle.  Under the mentorship of Eriq Augustine, my goal is to maximize Moodle's integration with the toolkit's defined functionality.

In my first week of development, I have completed the functionality to [list course users](https://github.com/edulinq/lms-toolkit/commit/45753113d64273dc8982000c37e4563b1a1f3b91) in Moodle. Moodle lacks an API and consequently seemingly simple procedures such as this become more complicated to implement. Listing course users properly required parsing the raw HTML and extracting the users, removing unnecessary data to reduce test data file sizes, and standardizing random data in the stored responses.  

I look forward to making more progress on the LMS-Toolkit for Moodle, one tool at a time!

My project proposal can be found here: [Proposal](https://docs.google.com/document/d/1Phev-RkKLhraQYX2kRzRAgZ19x65judBEN61HA7HZu8)
