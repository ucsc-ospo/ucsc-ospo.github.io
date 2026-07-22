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
Hello! My name is Jake Kelman and, through UCSC OSPO and GSoC 2026, I have been developing the [LMS-Toolkit](https://github.com/edulinq/lms-toolkit) functionality for [Moodle](https://moodle.org/) for around six weeks.
After completing the listing course users tool at the start of the project, I have since focused my efforts listing assignments in a given course.
Listing assignments in Moodle involves two primary steps: loading the assignments test data into the Moodle Docker image and fetching this data.

Due to lack of an API, programmatically loading the assignments is not a straightforward task.
The approach I took required meticulously investigating the changes to Moodle's [MySQL](https://www.oracle.com/mysql/what-is-mysql/) database before and after adding an assignment in the browser.
The generally obscure nature of the database, as well as the circular dependencies within it, added to the complexity of this task.
After countless trials and errors, I was eventually able to determine which database tables needed to be updated and how to update them properly for an assignment to be registered in the [LMS](https://en.wikipedia.org/wiki/Learning_management_system).
The triumph I felt when I saw the assignments in listed on the general course page cannot be understated.
However, this feeling subsided when an error appeared upon navigating to the grade book page.
I needed the grade book page to display the assignments successfully because it is where all the assignments' attributes, including the maximum points values, can be found.
After further delving into the database, I finally determined the additional necessary table updates to achieve a functional grade book.

Initially, I anticipated that fetching the assignments test data would be trivial as I had written similar code to fetch the users.
Nonetheless, there was an unforeseen hurdle I needed to overcome.
I needed to enable [Edit Mode](https://docs.moodle.org/19/en/Turn_editing_on) as this allowed the aforementioned maximum points values to appear.
Therefore, I investigated the request sent to the server when Edit Mode was toggled on in the browser and worked to mimmic this procedure in my code.
The first few attempts were unsuccessful but in time, with the help of my mentor, Eriq Augustine, I was able to execute the request correctly.

Ultimately, I was able to achieve the courses assignments list functionality.
Through my trials and tribulations, I am much more well versed in my understanding of a wide array of programming concepts.
I look forward to furthering my work on the LMS-Toolkit and deepening my technical expertise along the way!
