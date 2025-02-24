---
title: "LMS Toolkit"
authors: [eaugusti]
author_notes: ["Postdoctoral Researcher, LINQS Lab, UC Santa Cruz"]
tags: ["osre25", "uc", "software development", "teaching tools", "backend"]
date: 2025-02-06T13:00:00-08:00
lastmod: 2025-02-06T13:00:00-08:00
---

The [EduLinq LMS Toolkit](https://github.com/edulinq/py-canvas) (also called the "Canvas Tool" or "py-canvas") is a suite of tools used by several courses at UCSC
to interact with Canvas from the command line or Python.
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

Currently, the LMS Toolkit only supports Canvas, but this suite of projects hopes to not only expand existing support,
but add support for more LMSs.

### Advanced Canvas Support

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, rest api, data munging, http request inspection, python
 - **Difficulty:** Moderate
 - **Size:** Medium or Large (175 or 350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre25@gmail.com), [Batuhan Salih](mailto:linqs.osre25@gmail.com), [Lise Getoor](mailto:linqs.osre25@gmail.com)

The LMS Toolkit already has basic read-write support for core Canvas functionality (working with grades and assignments).
However, there are still many more features that can be supported such as
[group management](https://github.com/edulinq/py-canvas/issues/17),
[quiz management](https://github.com/edulinq/py-canvas/issues/7),
[quiz statistics](https://github.com/edulinq/py-canvas/issues/10),
and [assignment statuses](https://github.com/edulinq/py-canvas/issues/19).

The task for this project is to implement chose of set of advanced Canvas features to support
(not limited to those features mentioned above),
design an LMS-agnostic way to support those features,
and implement those features.
The flexibility in the features chosen to implement account for the variable size of this project.

See Also:
 - [Repository for LMS Toolkit](https://github.com/edulinq/py-canvas)
 - GitHub Issues
   - [Group Management](https://github.com/edulinq/py-canvas/issues/17),
   - [Quiz Management](https://github.com/edulinq/py-canvas/issues/7),
   - [Quiz Statistics](https://github.com/edulinq/py-canvas/issues/10),
   - [Assignment Statuses](https://github.com/edulinq/py-canvas/issues/19).

### New LMS Support: Moodle

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, rest api, data munging, http request inspection, python
 - **Difficulty:** Moderate
 - **Size:** Large (350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre25@gmail.com), [Batuhan Salih](mailto:linqs.osre25@gmail.com), [Lise Getoor](mailto:linqs.osre25@gmail.com)

The goal of the LMS toolkit is to provide a single interface for all LMSs.
It is a lofty goal, however there is currently only support for [Canvas](https://en.wikipedia.org/wiki/Instructure#Canvas).
[Moodle](https://en.wikipedia.org/wiki/Moodle) is one of the more popular LMSs.
Naturally, the LMS Toolkit wants to support Moodle as well.
Moodle is open source, so adding support in the LMS Toolkit should not be too challenging.

The task for this project is to add basic support for the Moodle LMS.
It is not necessary to support all the same features that are supported for Canvas,
but at least the core features of score and assignment management should be implemented.

See Also:
 - [Repository for LMS Toolkit](https://github.com/edulinq/py-canvas)
 - [Moodle Wiki Page](https://en.wikipedia.org/wiki/Moodle)
 - [GitHub Issue](https://github.com/edulinq/py-canvas/issues/22)

### New LMS Support: Blackboard

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, rest api, data munging, http request inspection, python
 - **Difficulty:** Challenging
 - **Size:** Large (350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre25@gmail.com), [Batuhan Salih](mailto:linqs.osre25@gmail.com), [Lise Getoor](mailto:linqs.osre25@gmail.com)

The goal of the LMS toolkit is to provide a single interface for all LMSs.
It is a lofty goal, however there is currently only support for [Canvas](https://en.wikipedia.org/wiki/Instructure#Canvas).
[Blackboard](https://en.wikipedia.org/wiki/Blackboard_Learn) (also called "Blackboard Learn") is one of the more popular LMSs.
Naturally, the LMS Toolkit wants to support Blackboard as well.
However, a challenge in supporting Blackboard is that it is not open source (unlike Canvas).
Therefore, support and testing on Blackboard may be very challenging.

The task for this project is to add basic support for the Blackboard LMS.
It is not necessary to support all the same features that are supported for Canvas,
but at least the core features of score and assignment management should be implemented.
The closed nature of Blackboard makes this a challenging and uncertain project.

See Also:
 - [Repository for LMS Toolkit](https://github.com/edulinq/py-canvas)
 - [Blackboard Wiki Page](https://en.wikipedia.org/wiki/Blackboard_Learn)
 - [GitHub Issue](https://github.com/edulinq/py-canvas/issues/21)

### New LMS Support: Brightspace

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, rest api, data munging, http request inspection, python
 - **Difficulty:** Challenging
 - **Size:** Large (350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre25@gmail.com), [Batuhan Salih](mailto:linqs.osre25@gmail.com), [Lise Getoor](mailto:linqs.osre25@gmail.com)

The goal of the LMS toolkit is to provide a single interface for all LMSs.
It is a lofty goal, however there is currently only support for [Canvas](https://en.wikipedia.org/wiki/Instructure#Canvas).
[D2L Brightspace](https://en.wikipedia.org/wiki/D2L#Brightspace) is one of the more popular LMSs.
Naturally, the LMS Toolkit wants to support Brightspace as well.
However, a challenge in supporting Brightspace is that it is not open source (unlike Canvas).
Therefore, support and testing on Brightspace may be very challenging.

The task for this project is to add basic support for the Brightspace LMS.
It is not necessary to support all the same features that are supported for Canvas,
but at least the core features of score and assignment management should be implemented.
The closed nature of Brightspace makes this a challenging and uncertain project.

See Also:
 - [Repository for LMS Toolkit](https://github.com/edulinq/py-canvas)
 - [Brightspace Wiki Page](https://en.wikipedia.org/wiki/D2L#Brightspace)
 - [GitHub Issue](https://github.com/edulinq/py-canvas/issues/23)

### Testing / CI Infrastructure

 - **Topics:** `Backend` `Teaching Tools` `Testing` `CI`
 - **Skills:** software development, backend, testing, ci, docker
 - **Difficulty:** Challenging
 - **Size:** Large (350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre25@gmail.com), [Batuhan Salih](mailto:linqs.osre25@gmail.com), [Lise Getoor](mailto:linqs.osre25@gmail.com)

The goal of the LMS toolkit is to provide a single interface for all LMSs.
This means that our system must communicate with several different (the LMSs),
each with their own systems, data patterns, versions, and quirks.
Testing will be essential to ensure that our tools keep working as the different LMSs evolve and update.
The LMS Toolkit currently tests with Canvas by
[mocking API responses](https://github.com/edulinq/py-canvas/tree/main/tests/api/test_cases).
However, this tactic does not scale well with multiple LMSs (and multiple versions of each system).
A more scalable approach would be to have test instances of the different LMSs that our testing infrastructure can interact with
both interactively and in [continuous integration](https://en.wikipedia.org/wiki/Continuous_integration) (CI).

The task for this project is to create testing infrastructure that
connects to test instances of different LMS systems (e.g., Canvas).
This task does not require that all the LMSs in this document are used,
but the testing infrastructure should be robust enough to support them all.
The open source LMSs (Canvas and Moodle) will likely be much easier to setup than the others,
and should be targeted first.
We should be able to run tests locally as well as in CI,
and will likely heavily use [Docker](https://en.wikipedia.org/wiki/Docker_(software)) containers.

See Also:
 - [Repository for LMS Toolkit](https://github.com/edulinq/py-canvas)
 - [GitHub Issue](https://github.com/edulinq/py-canvas/issues/24)
 - [Mocked API Responses](https://github.com/edulinq/py-canvas/tree/main/tests/api/test_cases).
