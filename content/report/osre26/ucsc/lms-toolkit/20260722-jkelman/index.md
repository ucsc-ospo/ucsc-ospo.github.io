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
Through UCSC OSPO and GSoC 2026, I have been developing the [LMS Toolkit](https://github.com/edulinq/lms-toolkit) functionality for [Moodle](https://moodle.org/) for around six weeks.
The LMS Tookit provides a set of tools and python interface for [learning management systems](https://en.wikipedia.org/wiki/Learning_management_system) (LMSs) such as Canvas, Moodle, and Blackboard.
After completing the course-specific tools including loading and fetching courses and course users, I have since focused my efforts on assignment-specific tools.
Like most toolkit functions, listing assignments in Moodle involves two primary steps: loading the test data into the Moodle Docker image and fetching this data.

Due to Moodle's lack of an API for adding assignments, programmatically loading them is not a straightforward task.
The approach I took required investigating the changes to Moodle's [MySQL](https://www.oracle.com/mysql/what-is-mysql/) database before and after adding an assignment in the browser.
The generally obscure nature of the database, as well as the circular dependencies within it, added to the complexity of this task.
After a number of iterations, I was eventually able to determine which database tables needed to be updated and how to update them properly for an assignment to be registered in the LMS.
Although the assignments were now shown on the general course page, an error appeared upon navigating to the grade book page.
I needed the grade book page to display the assignments accurately because it contains all the essential assignments' attributes, including the maximum points values.
After further delving into the database, I finally determined the additional necessary table updates to achieve a functional grade book.

Initially, I anticipated that fetching the assignments test data would be trivial as I had written similar code to fetch the users.
Nonetheless, there was an unforeseen hurdle to overcome.
I needed to enable a special setting that caused the aforementioned maximum points values to appear.
Therefore, I investigated the request sent to the server when this setting was toggled on in the browser and worked to mimmic this procedure in my code.
The first few attempts were unsuccessful but in time, with the help of my mentor, Eriq Augustine, I was able to execute the request correctly.

Ultimately, I was able to achieve the courses assignments list functionality.
Navigating these obstacles significantly expanded my knowledge of key programming concepts.
I now have a better understanding of the browser developer tools, the behaviors of relational databases, and the fundamental difference between interpreted and compiled programming languages.
I look forward to furthering my work on the LMS Toolkit and deepening my technical expertise along the way!

You can find my first blog post [here](https://ucsc-ospo.github.io/report/osre26/ucsc/lms-toolkit/20260613-jkelman/).
