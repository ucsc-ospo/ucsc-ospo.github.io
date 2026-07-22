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
This summer I have been developing the [LMS Toolkit](https://github.com/edulinq/lms-toolkit) functionality for [Moodle](https://moodle.org/) for around six weeks.
The LMS Tookit provides a set of tools and Python interface for [learning management systems](https://en.wikipedia.org/wiki/Learning_management_system) (LMSs) such as Canvas, Moodle, and Blackboard.
After completing the course- and user-specific tools, I have since focused my efforts on assignment-specific tools.
Like most LMS Toolkit functionality, listing assignments in Moodle involves two primary steps: loading the test data into a [Moodle Docker image](https://github.com/edulinq/lms-docker-moodle-testdata) and fetching data from Moodle.

Due to Moodle's lack of an API for adding assignments, programmatically loading them is not a straightforward task.
The approach included investigating the changes to Moodle's [MySQL](https://www.oracle.com/mysql/what-is-mysql/) database before and after adding an assignment in the browser.
The generally obscure nature of the database, as well as the circular dependencies within it, added to the complexity of this task.
After a number of iterations, I was eventually able to determine which database tables needed to be updated and how to update them properly for the assignments to be registered in the LMS.
However, only a general overview of the assignments was available upon the first successful load.
With a bit more research and additional database table updates, I achieved a functional grade book page to fetch all essential assignment data.

Initially, I anticipated that fetching an assignment's data would be trivial as I had written similar code to fetch the users.
Nonetheless, there was an unforeseen hurdle to overcome.
By default, the assignments' maximum points were missing from the assignment information.
I learned that a special setting needed to be enabled in order for the maximum points values to appear.
I examined the request sent to the server when this setting was toggled on in the browser and worked to mimmic this procedure in my code.
The first few attempts were unsuccessful but in time, with the help of my mentor, Eriq Augustine, I was able to execute the request correctly.

Ultimately, I was able to get information about all course assignments.
Navigating these obstacles significantly expanded my knowledge of key programming concepts.
I now have a better understanding of the browser developer tools, the behaviors of relational databases, and the fundamental difference between interpreted and compiled programming languages.
I look forward to furthering my work on the LMS Toolkit and deepening my technical expertise along the way!

You can find my first blog post [here](https://ucsc-ospo.github.io/report/osre26/ucsc/lms-toolkit/20260613-jkelman/).
