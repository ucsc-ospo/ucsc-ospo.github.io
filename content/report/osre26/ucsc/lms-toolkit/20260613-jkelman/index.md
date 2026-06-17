---
title: "LMS Toolkit: Expanding Support for Moodle"
subtitle: ""
summary:
authors:
  - jkelman
tags: ["osre26", "gsoc", "lms-toolkit", "CLI", "python", "lms"]
categories: ["GSoC 2026", "LMS-Toolkit"]
date: 2026-06-13
lastmod: 2026-06-13
featured: true
draft: false
image:
  focal_point: "Center"
  preview_only: false
---
Hi! I am Jake Kelman, a novice open source software developer.
Most of my current work involves programming [Google Apps Scripts](https://developers.google.com/apps-script) to help automate department workflows and improve visibility of data via automated emails.
I have enjoyed developing applications like an iOS word game and a [Pai gow Poker](https://en.wikipedia.org/wiki/Pai_gow_poker) desktop game.
I am excited for the opportunity to further improve my skills and assist the open source community.
Through Google Summer of Code via the LINQS Lab, I will be contributing to the [LMS-Toolkit](/project/osre26/ucsc/lms-toolkit) project this summer!

The LMS-Toolkit includes a python interface with many different CLI tools used to interact with a [Learning Management System](https://en.wikipedia.org/wiki/Learning_management_system) (LMS) such as Canvas, Moodle, or Blackboard.
Examples of the LMS Toolkit's functionality include listing courses, users (i.e., students and staff), gradebooks, assignments, and quizzes.
All of these tools are available for the Canvas LMS, but have not yet been implemented for Moodle.
Under the mentorship of Lise Getoor, Eriq Augustine, and Lucas Ellenberger, my goal is to implement as much Moodle functionality as possible.

In my first week of development, I have completed the functionality to [list the users in a Moodle course](https://github.com/edulinq/lms-toolkit/commit/45753113d64273dc8982000c37e4563b1a1f3b91).
Moodle lacks an API and consequently seemingly simple procedures such as this can be complicated to implement.
Listing a course's users properly required parsing HTML and extracting the users, removing unnecessary data to reduce test data file sizes, and standardizing random data in the stored responses.

I look forward to making more progress on the LMS-Toolkit for Moodle, one tool at a time!

My project proposal can be found [here](https://docs.google.com/document/d/1Phev-RkKLhraQYX2kRzRAgZ19x65judBEN61HA7HZu8).
