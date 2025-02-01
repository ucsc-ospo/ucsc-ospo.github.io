---
title: "Type Narrowing: A Language Design Benchmark"
authors: [bennn]
author_notes: ["University of Utah"]
tags: [osre25, reproducibility, "programming languages", types]
date: 2025-02-01
lastmod: 2025-02-01
---

Untyped languages such as JavaScript and Python provide a flexible starting
point for software projects, but eventually, the lack of reliable types
makes code hard to debug and maintain.
Gradually typed languages such
as
[TypeScript](https://www.typescriptlang.org/),
[Flow](https://flow.org/),
[Mypy](https://www.mypy-lang.org/),
and
[Pyright](https://microsoft.github.io/pyright/#/)
address the problem with type checkers that can reason about an
ever-growing subset of untyped code.
Widening the subset to precisely reason about untyped programming
patterns is an ongoing challenge.

Type narrowing is a key feature of gradual languages.
Narrowing uses type tests in code to refine types and push
information forward along the paths that the program may follow.
For example, when a type test checks an object field, later
code can trust the type of the field:

```
// item :: JSON Object
if typeof(item["price"] == "number"):
    // item :: JSON Object,
    //  where field "price" :: Number
    return item["price"] + (item["price"] * 0.30) // add tax
```

Nearly every gradual language agrees that _some form_ of type narrowing is needed.
There is widespread disagreement about how much support is enough, however.
TypeScript lets users define custom type tests, but it does not analyze
those tests to see whether they are reliable.
Flow does analyze tests.
TypeScript does not allow asymmetric type tests, but Flow, Mypy and Pyright
all do!
None of the above track information compositionally through program
execution, but Typed Racket (another gradual language) does --- is the
extra machinery in Typed Racket really worth the effort?

The goal of this project is to rigorously study type narrowing in practice
and identify tradeoffs to inform language designs.

Related Work:
* Type Narrowing in TypeScript
  <https://www.typescriptlang.org/docs/handbook/2/narrowing.html>
* Type Narrowing in Python
  <https://typing.readthedocs.io/en/latest/spec/narrowing.html#typeguard>
* Logical Types for Untyped Languages
  <https://doi.org/10.1145/1863543.1863561>


### Evaluate New Gradual Languages

* Topics: `benchmark implementation`, `programming languages`, `types`
* Skills: Ruby, Lua, Python, Clojure, PHP
* Difficulty: Medium
* Size: Small
* Mentor: {{% mention bennn %}}

Bring the If-T Benchmark to new typecheckers.
Examples include
[Sorbet]https://sorbet.org/(),
[Hack](https://hacklang.org/),
[Luau](https://luau.org/),
[Pyre](https://pyre-check.org/),
[Cinder / Static Python](https://github.com/facebookincubator/cinder),
[Typed Clojure](https://typedclojure.org/),
and
(potentially) [Elixir](https://elixir-lang.org/blog/2024/06/12/elixir-v1-17-0-released/).
Conduct a scientific, cross-language analysis to discuss the implications
of benchmark results.


### Do Unsound Narrowings Lead to Exploits?

* Topics: `corpus study`, `types`, `counterexamples`
* Skills: TypeScript, Python
* Difficulty: Medium
* Size: Small
* Mentor: {{% mention bennn %}}

Investigate type narrowing in practice through a corpus study of software projects.
Use the GitHub or Software Heritage APIs to search code for user-defined predicates
and other instances of narrowing. Search for vulnerabilities due to the unsound
typing of user-defined predicates.

