---
title: "HAgent"
authors: [renau]
author_notes: ["Professor, University of California Santa Cruz"]
tags: ["osre25", "uc", "hardware design agents"]
date: 2025-02-11
lastmod: 2025-02-11
---

[HAgent](https://github.com/masc-ucsc/hagent) is a platform to build AI hardware agent engine to support multiple components in chip design, such as code generation, verification, debugging, and tapeout.

HAgent is build as a compiler for for Hardware Agents, it interfaces with
typical EDA tools like compilers, synthesis, and verification. There are
several projects around enhancing HAgent.


### BugFarm hagent step

**Objective**: Develop a HAgent step (pass) to create bugs in a given design.


**Description**: Using LLMs (Hagent APIs), the goal is to add "bugs" to input Verilog design.
The goal is for other tools passes that need to fix bugs, to use this
infrastructure as a bug generator. There is a MCY
(https://github.com/YosysHQ/mcy) that does something similar but it does not
use verilog and create a very different Verilog output. The BugFarm is supposed
to have somewhat similar functionality but edit the Verilog directly which
results in a code with just a few edits. Like MCY, there has to be a step to confirm that
the change affects results. The project should benchmarks and compare with MCY.

- **Skills Needed:** Python, Verilog, and understand agents
- **Difficulty:** Medium
- **Size:** Medium
- **Mentors:** {{% mention "renau" %}}, {{% mention "frabieik" %}}

### HDEval Competition Repository

**Objective**: Create a platform for HDL programming challenges and community engagement.

**Description**: Develop a repository where users can solve HDL problems in Verilog, Chisel, PyRTL, etc. Implement a points system for successful solutions. Allow users to submit new problems (code, specifications, verification, and tests) that are not easily solvable by LLMs. Automate solution testing and provide feedback on submissions.

The submissions consist of 4 components: code, specification, verification, and tests. It should be possible to submit also examples of bugs in code/specification/verification/tests during the design.

If the code is different from Verilog, it should include the HDL (chisel, PyRTL,...) and also the Verilog.

The specification is free form. For any given specification, an expert on the area should be able to generate code, verification, and tests. Similarly, from any pair. Any expert should be able to generate the rest. For example, from verification and tests, it should be able to generate the code and specification.

Typical specifications consist of a plan, API, and a sample usage.

- **Skills Needed:**  Web design, some hardware understanding
- **Difficulty:** Medium
- **Size:** Medium
- **Mentors:** {{% mention "renau" %}}, {{% mention "frabieik" %}}

### Integrate Silicon Compiler

**Objective**: [Silicon Compiler](https://github.com/siliconcompiler/siliconcompiler) is an open-source Python library that allows to interface with many EDA tools. The idea is to integrate it with HAgent to allow prompts/queries to 
interface with it.


**Description**: The agentic component requires to check with silicon compiler
that the generated Python compiles but also that has reasonable parameters.
This will require a react loop for compiler errors, and likely a judge loop for
testing for reasonable options/flow with feedback from execution. Since there
is not much training examples, it will require a few shot with a database to
populate context accordingly.

The end result should allow to select different tools and options trhough silicon compiler. 

- **Skills Needed:**  Backend chip design
- **Difficulty:** High
- **Size:** Medium
- **Mentors:** {{% mention "renau" %}}


### Comodore 64 or MSX or Gameboy

**Objective**: Create a prompt-only specification to build a hardware
accelerated for the target platform (Comodore 64, MSX or Gameboy). The
generated code should focus on Verilog, but it is fine to also target some
other HDL. In all the cases, the project should include a generated Verilog
integrated with some emulator for verification.

**Description**: Using [Hagent](https://github.com/masc-ucsc/hagent), create an
[HDLEval](https://github.com/masc-ucsc/hdeval) benchmark (set of prompts) that
provide the necessary information to create the Verilog implementation. HDLEval
prompts usually consists of a high-level PLAN or specification, an API to
implement, and a few examples of usage for the given API.

The result of running the bencharmk, a  generated Verilog runs program in the
emulator and the Verilog to compare correctness. The platform should have an
already existing emulator [vice-emu](https://vice-emu.sourceforge.io/) or
[mGBA](https://mgba.io/) to perform cosimulation against the generated
specification.

- **Skills Needed:**  Verilog for front-end design
- **Difficulty:** High
- **Size:** Large (175 or 350 hours)
- **Mentors:** {{% mention "renau" %}}

