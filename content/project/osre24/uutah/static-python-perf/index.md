---
title: "Static Python Perf: Measuring the Cost of Sound Gradual Types"
authors: [bennn]
author_notes: ["University of Utah"]
tags: [osre24, reproducibility, "programming languages", python, types]
date: 2024-01-06
lastmod: 2024-01-06
---

Gradual typing is a solution to the longstanding tension between typed and
untyped languages: let programmers write code in any flexible language (such
as Python), equip the language with a suitable type system that can describe
invariants in part of a program, and use run-time checks to ensure soundness.

For now, though, the cost of run-time checks can be enormous.
Order-of-magnitude slowdowns are common. This high cost is a main reason why
TypeScript is unsound by design --- its types are not trustworthy in order
to avoid run-time costs.

Recently, a team at Meta built a gradually-typed variant of Python called
(*drumroll*) Static Python. They report an incredible 4% increase in CPU
efficiency at Instagram thanks to the sound types in Static Python. This
kind of speedup is unprecedented.

Other languages may want to follow the Static Python approach to gradual types,
but there are big reasons to doubt the Instagram numbers:
* the experiment code is closed source, and
* the experiment itself is not easily reproducible (even for Instagram!).

Static Python needs a rigorous, reproducible performance evaluation to test
whether it is indeed a fundamental advance for gradual typing.

Related Work:
* Gradual Soundness: Lessons from Static Python
  <https://programming-journal.org/2023/7/2/>
* Producing Wrong Data Without Doing Anything Obviously Wrong!
  <https://users.cs.northwestern.edu/~robby/courses/322-2013-spring/mytkowicz-wrong-data.pdf>
* On the Cost of Type-Tag Soundness
  <https://users.cs.utah.edu/~blg/resources/pdf/gm-pepm-2018.pdf>

### Design and Run an Experiment

* Topics: `performance`, `cluster computing`, `statistics`
* Skills: Python AST parsing, program generation, scripting, measuring performance
* Difficulty: Medium
* Size: Medium (175 hours)
* Mentor: Ben Greenman

Design an experiment that covers the space of gradually-typed Static Python programs
in a fair way. Since every variable in a program can have up to 3 different types,
there are easily 3^20 possibilities in small programs --- far too many to measure
exhaustively.

Run the experiment on an existing set of benchmarks using a cluster such as CloudLab.
Manage the cluster machines across potentially dozens of reservations and combine
the results into one comprehensive view of Static Python performance.


### Derive Benchmarks from Python Applications

* Topics: `types`, `optimization`, `benchmark design`
* Skills: Python
* Difficulty: Medium
* Size: Small to Large
* Mentor: Ben Greenman

Build or find realistic Python applications, equip them with rich types,
and modify them to run a meaningful performance benchmark. Running a benchmark
should produce timing information, and the timing should not be significantly
influenced by random variables, I/O actions, or system events.


