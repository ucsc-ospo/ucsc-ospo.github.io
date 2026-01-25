---
title: "LMS Toolkit"
authors: [eaugusti]
author_notes: ["Postdoctoral Researcher, LINQS Lab, UC Santa Cruz"]
tags: ["osre26", "uc", "linqs", "software development", "teaching tools", "backend"]
date: 2026-01-13T13:00:00-08:00
lastmod: 2026-01-13T13:00:00-08:00
---

The [EduLinq LMS Toolkit](https://github.com/edulinq/lms-toolkit) is a suite of tools used by several courses at UCSC
to interact with LMS's (e.g. Canvas) from the command line or Python.
A [Learning Management System](https://en.wikipedia.org/wiki/Learning_management_system) (LMS) is a system that institutions use to manage courses, assignments, students, and grades.
The most popular LMSs are
[Canvas](https://en.wikipedia.org/wiki/Instructure#Canvas),
[Blackboard](https://en.wikipedia.org/wiki/Blackboard_Learn),
[Moodle](https://en.wikipedia.org/wiki/Moodle),
and [Brightspace](https://en.wikipedia.org/wiki/D2L#Brightspace).
These tools can be very helpful, especially from an administrative standpoint, but can be hard to interact with.
They can be especially difficult when instructors and TAs want to do something that is not explicitly supported by their built-in GUIs
(e.g., when an instructor wants to use a special grading policy).
The LMS Toolkit project is an effort to create a single suite of command-line tools (along with a Python interface)
to connect to all the above mentioned LMSs in a simple and uniform way.
So, not only can instructors and TAs easily access the modify the data held in an LMS (like a student's grades),
but they can also do it the same way on any LMS.
The [LINQS Lab](https://linqs.org) has made many contributions to the maintain and improve the Quiz Composer.

Currently, the LMS Toolkit supports Canvas, Moodle, and Blackboard.
But, the degree of support for each LMS varies.

All students interested in LINQS projects for OSRE/GSoC 2026 should fill out [this form](https://forms.gle/Mr4YR3N35pWDb4uz7).
Towards the end of the application window, we will contact those who we believe to be a good fit for a LINQS project.
The form will stop accepting responses once the application window closes.
Do not post on any of the project repositories about OSRE/GSoC
(e.g., comment on an issue that you want to tackle it as a part of OSRE/GSoC 2026).
Remember, these are active repositories that were not created for OSRE/GSoC.

### Advanced LMS Support

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, rest api, data munging, http request inspection, python
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre26@gmail.com), [Batuhan Salih](mailto:linqs.osre26@gmail.com), [Lise Getoor](mailto:linqs.osre26@gmail.com)

The LMS Toolkit already has basic read-write support for many core pieces of LMS functionality (e.g., working with grades and assignments).
However, there are still many more features that can be supported such as
[group management](https://github.com/edulinq/lms-toolkit/issues/17),
[quiz management](https://github.com/edulinq/lms-toolkit/issues/7),
[quiz statistics](https://github.com/edulinq/lms-toolkit/issues/10),
and [assignment statuses](https://github.com/edulinq/lms-toolkit/issues/19).

The task for this project is to choose a set of advanced features
(not limited to those features mentioned above),
design an LMS-agnostic way to support those features,
and implement those features.
The flexibility in the features chosen to implement account for the variable size of this project.

See Also:
 - [Repository for LMS Toolkit](https://github.com/edulinq/lms-toolkit)
 - GitHub Issues
   - [Group Management](https://github.com/edulinq/lms-toolkit/issues/17),
   - [Quiz Management](https://github.com/edulinq/lms-toolkit/issues/7),
   - [Quiz Statistics](https://github.com/edulinq/lms-toolkit/issues/10),
   - [Assignment Statuses](https://github.com/edulinq/lms-toolkit/issues/19).

### New LMS Support: Brightspace

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, rest api, data munging, http request inspection, python
 - **Difficulty:** Challenging
 - **Size:** Large (350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre26@gmail.com), [Batuhan Salih](mailto:linqs.osre26@gmail.com), [Lise Getoor](mailto:linqs.osre26@gmail.com)

The goal of the LMS toolkit is to provide a single interface for all LMSs.
[D2L Brightspace](https://en.wikipedia.org/wiki/D2L#Brightspace) is one of the more popular LMSs.
Naturally, the LMS Toolkit wants to support Brightspace as well.
However, a challenge in supporting Brightspace is that it is not open source (unlike Canvas and Moodle).
Therefore, support and testing on Brightspace may be very challenging.

The task for this project is to add basic support for the Brightspace LMS.
It is not necessary to support all the same features that are supported for other LMSs,
but at least the core features of score and assignment management should be implemented.
The closed-source nature of Brightspace makes this a challenging and uncertain project.

See Also:
 - [Repository for LMS Toolkit](https://github.com/edulinq/lms-toolkit)
 - [Brightspace Wiki Page](https://en.wikipedia.org/wiki/D2L#Brightspace)
 - [GitHub Issue](https://github.com/edulinq/lms-toolkit/issues/23)
