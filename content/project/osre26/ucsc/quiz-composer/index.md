---
title: "Quiz Composer"
authors: [eaugusti]
author_notes: ["Postdoctoral Researcher, LINQS Lab, UC Santa Cruz"]
tags: ["osre26", "uc", "linqs", "software development", "teaching tools", "backend"]
date: 2026-01-13T13:00:00-08:00
lastmod: 2026-01-13T13:00:00-08:00
---

The [EduLinq Quiz Composer](https://github.com/edulinq/quiz-composer) (also called the "Quiz Generator") is a tool used by several courses at UCSC
to create and maintain platform-agnostic quizzes (including exams and worksheets).
Knowledge assessments like quizzes, exams, and tests are a core part of the learning process for many courses.
However maintaining banks of questions, collaborating on new questions, and converting quizzes to new formats can use up a lot of time,
taking time away from actually working on improving course materials.
The Quiz Composer helps by providing a single text-based format that can be stored in a repository and "compiled" into many different formats including:
HTML, LaTeX, PDF, Canvas, GradeScope, and QTI.
The [LINQS Lab](https://linqs.org) has made many contributions to the maintain and improve the Quiz Composer.

As an open source project, there are endless opportunities for development, improvements, and collaboration.
Here, we highlight some specific projects that will work well in the summer mentorship setting.

All students interested in LINQS projects for OSRE/GSoC 2026 should fill out [this form](https://forms.gle/Mr4YR3N35pWDb4uz7).
Towards the end of the application window, we will contact those who we believe to be a good fit for a LINQS project.
The form will stop accepting responses once the application window closes.
Do not post on any of the project repositories about OSRE/GSoC
(e.g., comment on an issue that you want to tackle it as a part of OSRE/GSoC 2026).
Remember, these are active repositories that were not created for OSRE/GSoC.

### Canvas Import

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, rest api, data munging, http request inspection, python
 - **Difficulty:** Moderate
 - **Size:** Medium (175 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre26@gmail.com), [Lucas Ellenberger](mailto:linqs.osre26@gmail.com), [Lise Getoor](mailto:linqs.osre26@gmail.com)

The Quiz Composer houses quizzes and quiz questions in a simple and unambiguous format based
on [JSON](https://en.wikipedia.org/wiki/JSON) and [Markdown](https://en.wikipedia.org/wiki/Markdown) (specifically, the [CommonMark specification](https://commonmark.org)).
This allows the Quiz Composer to unambiguously create versions of the same quiz in many different formats.
However, creating a quiz in the Quiz Composer format can be a daunting task for those not familiar with JSON or Markdown.
Instead, it would be easier for people to import quizzes from another format into the Quiz Composer format,
and then edit it as they see fit.
Unfortunately not all other quiz formats, namely Canvas in this case, are unambiguous.

The task for this project is to implement the functionality of importing quizzes from Canvas to the standard Quiz Composer format.
The unambiguous nature of Canvas quizzes makes this task non-trivial,
and adds an additional element of design decisions to this task.
It will be impossible to import quizzes 100% correctly,
but we want to be able to get close enough that most people can import their quizzes without issue.

See Also:
 - [Repository for Quiz Composer](https://github.com/edulinq/quiz-composer)
 - [GitHub Issue](https://github.com/edulinq/quiz-composer/issues/27)

### Google Forms Export

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, rest api, data munging, python
 - **Difficulty:** Moderate
 - **Size:** Medium (175 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre26@gmail.com), [Lucas Ellenberger](mailto:linqs.osre26@gmail.com), [Lise Getoor](mailto:linqs.osre26@gmail.com)

The Quiz Composer can export quizzes to many different formats,
each with a varying level of interactivity and feature support.
For example, quizzes can be exported to PDFs which will be printed and the students will just write down their answers to be checked in the future.
Quizzes can also be exported to interactive platforms like Canvas where students can enter answers that may be automatically checked with feedback immediately provided to the student.
On potential platform with functionality somewhere between the above two examples is [Google Forms](https://workspace.google.com/products/forms/).
"Forms" (an entity on Google Forms) can be something like a survey or (as of more recently) a quiz.

The task for this project is to add support for exporting quizzes from the Quiz Composer to Google Forms.
There is a large overlap in the quiz features supported in Canvas (which the Quiz Composer already supports) and Google Forms,
so most settings should be fairly straightforward.
There may be some design work around deciding what features are specific to one quiz platform
and what features can be abstracted to work across several platforms.

See Also:
 - [Repository for Quiz Composer](https://github.com/edulinq/quiz-composer)
 - [GitHub Issue](https://github.com/edulinq/quiz-composer/issues/19)

### Template Questions

 - **Topics:** `Backend` `Teaching Tools` `API`
 - **Skills:** software development, backend, data munging, python
 - **Difficulty:** Moderate-Challenging
 - **Size:** Large (350 hours)
 - **Mentors:** [Eriq Augustine](mailto:linqs.osre26@gmail.com), [Lucas Ellenberger](mailto:linqs.osre26@gmail.com), [Lise Getoor](mailto:linqs.osre26@gmail.com)

Questions in the Quiz Composer are described using [JSON](https://en.wikipedia.org/wiki/JSON) and [Markdown](https://en.wikipedia.org/wiki/Markdown)
files which contain the question prompt, possible answers, and the correct answer.
(Of course there are many differ [question types](https://github.com/edulinq/quiz-composer/blob/main/docs/question-types.md),
each with different semantics and requirements.)
However, a limitation of this is that each question is always the same.
You can have multiple copies of a question with slightly different prompts, numbers, and answers;
but you are still limited to each question being static and unchanging.
It would be useful to have "template questions" that can dynamically create static questions from a template
and collection of replacement data.

The task for this project is to add support for the "template questions" discussed above.
Much of the high-level design work for this issue has [already been completed](https://github.com/edulinq/quiz-composer/issues/26).
But there is still the implementation and low-level design decision left to do.

See Also:
 - [Repository for Quiz Composer](https://github.com/edulinq/quiz-composer)
 - [GitHub Issue](https://github.com/edulinq/quiz-composer/issues/26)
