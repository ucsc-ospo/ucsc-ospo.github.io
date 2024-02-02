---
title: "LiveHD"
authors: ["Jose Renau"]
author_notes: ["Professor of Computer Science & Engineering, UC Santa Cruz"]
tags: ["osre24", "uc"]
date: 2024-02-01
lastmod: 2024-02-01
---


The goals is to enable a more productive flow where the ASIC/FPGA designer can
work with multiple hardware description languages like CHISEL, Pyrope, or
Verilog.

There are several projects, some compiler infrastructure around
[LiveHD](https://github.com/masc-ucsc/livehd). Others around how to interface
LLMs to improve chip design productivity.

There are the following projects available:
* Slang with LiveHD
* Hardware Hierarchical Dynamic Structures (hdds)
* HDLEval for LLMs
* C++ Profiler Optimizer with LLMs
* Decompiler from Assembly to C++ with LLMs


## Slang with LiveHD

### Project Idea

[slang](https://github.com/MikePopoloski/slang) is one of the best open source
Verilog front-ends available. [LiveHD](https://github.com/masc-ucsc/livehd)
uses slang, but only a subset of Verilog is supported. The goal is to add more slang features.


### Project Deliverable

The slang/LiveHD interface creates LiveHD IR (LNAST IR). The plan is to keep
extending the translation to support more features. This is a project that
allows small steps. The goal is to support all Verilog 2001, and potentially
some System Verilog features.

### Topics

SysteVerilog, Compilers

### Skills Needed

Knowledge of Verilog, C++17, some compiler background.

### Difficulty

Medium

### Size

Large

## Hardware Hierarchical Dynamic Structures (hdds)

### Project Idea

[hdds](https://github.com/masc-ucsc/hhds) aims to build efficient tree and
graph data structures commonly used by hardware compilers. A key difference is
the hierarchical nature, and patterns.


### Project Deliverable

There are 2 main components: Graph and Tree.

For each, there is a hierarchical implementation that allows to connect tree/graphs in a hieararchy. 
For example, a graph can call another graph with input and outputs like a Verilog module calls other Verilog modules. 

Both classes should have iterators for traversing in topological sort.

### Topics

Data structures for compilers.

### Skills Needed

Data structures, C++17

### Difficulty

Medium

### Size

Large

## HDLEval for LLMs

### Project Idea

LLMs can be used to create new hardware. The goal of this project is to create multiple prompts
so that LLM/compiler designers can have examples to improve their flows.

### Project Deliverable

The idea is to create many sample projects where a "input" creates a Verilog artifact. The specification should not assume Verilog as output because other HDLs like Chisel could be used. 

The goal is to create many sample circuits that are realistic and practical. The description can have 

### Topics

Verilog, LLMs

### Skills Needed

Verilog or Chisel

### Difficulty

Low

### Size

Small

## C++ Profiler Optimizer with LLMs

### Project Idea

Fine-tune, and/or RAG, a LLM to leverage profiling tools so that it can provide
code optimization recommendations for C++ and possibly Rust code.


### Project Deliverable

Create a Python package (poetry?) called aiprof that analyzes the execution of a C++ or Rust program and
provide code change recommendations to improve performance.

```
aiprof ./binary
```

aiprof uses perf tools but also other tools like redspy, zerospy, and loadspy
to find problematic code areas and drive the GPT optimizer.

The plan is to find several examples of transformations to have a database so
that a model like CodeLlama or mixtral can be fine-tuned with code optimization
recomendations.

### Topics

C++, perf tools

### Skills Needed

C++17, Linux performance counters

### Difficulty

Medium

### Size

Large

## Decompiler from Assembly to C++ with LLMs

### Project Idea

There are several decompilers from assembly to C like ghidra and retdec. The idea is to enhance
both outputs to feed an LLM to generate nicer C++ code.

### Project Deliverable


ghidra and retdec generate C code out of assembly. The idea is to start with
these tools as baseline, but feed it to a LLM to generate C++ code instead of
plain C.

Create a Python package (poetry?) called aidecomp that integrates both
decompilers. It allows to target C or C++17.

To check that the generated code is compatible with the function translated, a
fuzzer could be used. This allows aidecomp to iterate the generation if the
generated code is not equivalent.

### Topics

C++, decompilers

### Skills Needed

C++17

### Difficulty

Medium

### Size

Large

