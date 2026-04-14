---
title: "Lynx Grader"
authors: [eaugusti]
author_notes: ["Postdoctoral Researcher, LINQS Lab, UC Santa Cruz"]
tags: ["osre26", "uc", "linqs", "software development", "teaching tools", "data science", "ai", "ml", "llm", "frontend", "backend"]
date: 2026-01-13T13:00:00-08:00
lastmod: 2026-01-13T13:00:00-08:00
---

The [EduLinq Lynx Grader](https://github.com/edulinq/autograder-server) (also referred to as "autograder") is an open source tool used by several courses at UCSC
to safely and quickly grade programming assignments.
Grading student code is something that may seem simple at first (you just need to run their code!),
but quickly becomes exceeding complex as you get more into the details.
Specifically, grading a student's code securely while providing the "last mile" service of getting code from students
and sending results to instructors/TAs and the course's LMS (e.g., Canvas) can be very difficult.
The Lynx Grader provides all of this in a free and open source project.
The [LINQS Lab](https://linqs.org) has made many contributions to the maintain and improve the Lynx Grader.

As an open source project, there are endless opportunities for development, improvements, and collaboration.
Here, we highlight some specific projects that will work well in the summer mentorship setting.

All students interested in LINQS projects for OSRE/GSoC 2026 should fill out [this form](https://forms.gle/Mr4YR3N35pWDb4uz7).
Towards the end of the application window, we will contact those who we believe to be a good fit for a LINQS project.
The form will stop accepting responses once the application window closes.
Do not post on any of the project repositories about OSRE/GSoC
(e.g., comment on an issue that you want to tackle it as a part of OSRE/GSoC 2026).
Remember, these are active repositories that were not created for OSRE/GSoC.

### LLM Detection

 - **Topics:** `AI/ML` `LLM` `Research` `Backend`
 - **Skills:** software development, backend, systems, data munging, go, docker
 - **Difficulty:** Challenging
 - **Size:** Large (350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre26@gmail.com), [Fabrice Kurmann](mailto:linqs.osre26@gmail.com), [Lise Getoor](mailto:linqs.osre26@gmail.com)

As [Large Language Model (LLM)](https://en.wikipedia.org/wiki/Large_language_model) tools like ChatGPT become more common and powerful,
instructors need tools to help determine if students are the actual authors of the code they submit.
More classical instances of plagiarism are often discovered by code similarity tools like [MOSS](https://theory.stanford.edu/~aiken/moss/).
However these tools are not sufficient for detecting code written not by a student,
but by an AI model like [ChatGPT](https://en.wikipedia.org/wiki/ChatGPT) or [GitHub Copilot](https://en.wikipedia.org/wiki/GitHub_Copilot).

The task for this project is to create a system that provides a score indicating the system's confidence that a given piece of code was written by an AI tool and not a student.
This will supplement the existing code analysis tools in the Lynx Grader.
There are many approaches to completing this task that will be considered.
A more software development approach can consist of levering exiting systems to create a production-ready system,
whereas a more research approach can consist of creating a novel approach complete with a paper and experiments.

There has been [previous work on this issue](https://github.com/anvichip/AI-code-detection-ML/blob/main/experiment/report.md),
where a student did a survey of existing solutions, collection of initial datasets, and exploratory experiments on possible directions.
This project would build off of this previous work.

See Also:
 - [Repository for Lynx Grader Server](https://github.com/edulinq/autograder-server)
 - [GitHub Issue](https://github.com/edulinq/autograder-server/issues/140)

### Code Analysis GUI

 - **Topics:** `Frontend`
 - **Skills:** software development, frontend, data munging, js, css, go
 - **Difficulty:** Easy
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre26@gmail.com), [Fabrice Kurmann](mailto:linqs.osre26@gmail.com), [Lise Getoor](mailto:linqs.osre26@gmail.com)

The Lynx Grader has existing functionality to analyze the code in a student's submission for malicious content.
Relevant to this project is that the Lynx Grader can run a pairwise similarity analysis against all submitted code.
This is how most existing software plagiarism systems detect offending code.
The existing infrastructure provides detailed statistics on code similarity,
but does not currently have a visual way to display this data.

The task for this project is to create a web GUI using the Lynx Grader REST API
to display the results of a code analysis.
The size of this project depends on how many of the existing features are going to be supported by the web GUI.

See Also:
 - [Repository for Lynx Grader Web GUI](https://github.com/edulinq/autograder-web)
 - [GitHub Issue](https://github.com/edulinq/autograder-server/issues/142)
 - [Pairwise Code Analysis Type](https://github.com/edulinq/autograder-server/blob/main/internal/model/analysis.go#L78)
 - [Sample API Data](https://github.com/edulinq/autograder-py/blob/v0.6.16/tests/api/testdata/courses/assignments/analysis/courses_assignments_submissions_analysis_pairwise_wait.json)

### Web GUI

 - **Topics:** `Frontend`
 - **Skills:** software development, frontend, js, css
 - **Difficulty:** Easy
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre26@gmail.com), [Fabrice Kurmann](mailto:linqs.osre26@gmail.com), [Lise Getoor](mailto:linqs.osre26@gmail.com)

The Lynx Grader contains dozens of [API endpoints](https://github.com/edulinq/autograder-server/blob/main/resources/api.json),
most directly representing a piece of functionality exposed to the user.
All of these features are exposed in the [Lynx Grader's Python Interface](https://github.com/edulinq/autograder-py).
However, the Python interface is a purely command-line interface.
And although command-line interface are objectively (read: subjectively) the best,
a web GUI would be more accessible to a wider audience.
The autograder already has a [web GUI](https://github.com/edulinq/autograder-web),
but it does not cover all the features available in the Lynx Grader.

The task for this project is to augment the Lynx Grader's web GUI with more features.
Specifically, add support for more tools used to create and administer courses.

See Also:
 - [Repository for Lynx Grader Web GUI](https://github.com/edulinq/autograder-web)
 - [GitHub Issue](https://github.com/edulinq/autograder-server/issues/61)
 - [Lynx Grader API Endpoints](https://github.com/edulinq/autograder-server/blob/main/resources/api.json)
 - [Lynx Grader's Python Interface](https://github.com/edulinq/autograder-py)
