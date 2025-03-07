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
Widening the subset with precise types is an ongoing challenge.

Furthermore, designs for precise gradual types need to be reproducible
across languages.
Ideas that works well in one language need to be validated
in other contexts in a principled, scientific way to separate
deep insights from language-specific hacks.

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

Nearly every gradual language agrees that _some form_ of type narrowing is needed,
but there is widespread disagreement about how much support is enough.
TypeScript lets users define custom type tests, but it does not analyze
those tests to see whether they are reliable.
Flow does analyze tests.
TypeScript does not allow asymmetric type tests (example: `is_even_number`),
but Flow, Mypy and Pyright all do!
None of the above track information compositionally through program
execution, but another gradual language called Typed Racket does
Is the extra machinery in Typed Racket really worth the effort?

Over the past several months, we have curated a language design
benchmark for type narrowing, **If-T**:

- <https://github.com/utahplt/ift-benchmark>

The benchmark presents type system challenges in a language-agnostic way
to facilitate reproducibility across languages.
It also includes a [_datasheet_](https://github.com/utahplt/ifT-benchmark/blob/main/DATASHEET.md)
to encourage cross-language comparisons
that focus on fundamental typing features rather than incidental difference
between languages.
So far, we have implemented the benchmark for five gradual languages.
There are many others to explore, and much more to learn.

The goal of this project is to replicate and extend the If-T type narrowing
benchmark.
Outcomes include a deep understanding of principled type narrowing,
and of how to construct a benchmark that enables reproducible
cross-language comparisons.

Related Work:
* Type Narrowing in TypeScript
  <https://www.typescriptlang.org/docs/handbook/2/narrowing.html>
* Type Narrowing in Python
  <https://typing.readthedocs.io/en/latest/spec/narrowing.html#typeguard>
* Logical Types for Untyped Languages
  <https://doi.org/10.1145/1863543.1863561>


### Evaluate New Gradual Languages

* Topics: `benchmark implementation`, `programming languages`, `types`
* Skills: Ruby, Lua, Python, Clojure, or PHP
* Difficulty: Medium
* Size: Small
* Mentor: {{% mention bennn %}}

Bring the If-T Benchmark to new typecheckers.
Examples include
[Sorbet](https://sorbet.org/),
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
* Skills: TypeScript or Python
* Difficulty: Medium
* Size: Small
* Mentor: {{% mention bennn %}}

Investigate type narrowing in practice through a corpus study of software projects.
Use the GitHub or Software Heritage APIs to search code for user-defined predicates
and other instances of narrowing. Search for vulnerabilities due to the unsound
typing of user-defined predicates.

