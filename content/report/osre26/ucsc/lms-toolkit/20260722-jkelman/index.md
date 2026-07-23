---
title: "LMS Toolkit: Listing Assignments in Moodle"
subtitle: ""
summary:
authors:
  - jkelman
tags: ["osre26", "gsoc", "lms-toolkit", "CLI", "python", "lms"]
categories: ["GSoC 2026", "LMS-Toolkit"]
date: 2026-07-22
lastmod: 2026-07-22
featured: true
draft: false
image:
  focal_point: "Center"
  preview_only: false
---
This summer, I have been developing the [LMS Toolkit](https://github.com/edulinq/lms-toolkit) functionality for [Moodle](https://moodle.org/).
The LMS Tookit provides a set of tools and Python interface for [learning management systems](https://en.wikipedia.org/wiki/Learning_management_system) (LMSs) such as Canvas, Moodle, and Blackboard.
After completing the course- and user-specific tools, I have since focused my efforts on assignment-specific tools.
Like most LMS Toolkit functionality, listing assignments in Moodle requires two primary steps: loading the test data into a [Moodle Docker image](https://github.com/edulinq/lms-docker-moodle-testdata) and fetching data from Moodle.

Due to Moodle's lack of an API for adding assignments, programmatically loading them is not a straightforward process.
My approach involved investigating the changes to Moodle's [MySQL](https://www.oracle.com/mysql/what-is-mysql/) database before and after adding an assignment in the browser.
The generally obscure nature of the database, as well as the circular dependencies within it, added to the complexity of this task.
After a number of iterations, I identified the necessary database table changes and how to apply them so assignments would register correctly in the LMS.
However, the system displaced only a general overview of the assignments upon the first successful load.
Through additional research and targeted database updates, all assignment data was integrated.

Initially, I expected fetching assignment data to be simple because I had already written similar code to fetch users.
Nonetheless, there was an unforeseen hurdle to overcome.
By default, the assignments' maximum points values were missing from the assignment information.
I learned that a special setting needed to be enabled in order for these values to appear.
I examined the requests sent to the server upon enabling this setting in the browser and worked to mimmic this procedure in my code.
The first few attempts were unsuccessful but in time, with the help of my mentor, Eriq Augustine, I was able to execute the requisite request properly.

Ultimately, I was able to get information about all course assignments.
Navigating these obstacles significantly expanded my knowledge of key programming concepts.
I now have a better understanding of the browser developer tools, the behaviors of relational databases, and the fundamental difference between interpreted and compiled programming languages.
I look forward to furthering my work on the LMS Toolkit and deepening my technical expertise along the way!

You can find my first blog post [here](https://ucsc-ospo.github.io/report/osre26/ucsc/lms-toolkit/20260613-jkelman/).
