---
title: "LiveHD"
authors: ["Jose Renau"]
author_notes: ["Professor of Computer Science & Engineering, UC Santa Cruz"]
tags: ["osre23", "uc"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

Projects for [LiveHD](https://github.com/masc-ucsc/livehd). Lead Mentors: [Jose Renau](mailto:renau@ucsc.edu) and [Sakshi Garg](mailto:sgarg3@ucsc.edu)

LiveHD is a "compiler" infrastructure for hardware design optimized for synthesis and simulation. The goals is to enable a more productive flow where the ASIC/FPGA designer can work with multiple hardware description languages like CHISEL, Pyrope, or Verilog.

There are several projects available around LiveHD. A longer explanation and more project options are available at
[projects](https://github.com/masc-ucsc/livehd/blob/master/docs/projects.md). Contact the
mentors to find a project that fits your interests.

A sample of helpful projects:

### Mockturtle

|   |   |
|---|---|
| Title | Mockturtle |
| Description | Perform synthesis for graph in LiveHD using Mockturtle |
| Mentor(s) | Jose Renau|
| Skills | C++17, synthesis |
| Difficulty | Medium |
| Size | Medium 175 hours|
| [Link](https://github.com/masc-ucsc/livehd/blob/master/docs/projects_large.md#medium-parallel-and-hierarchical-synthesis-with-mockturtle) |


Mockturtle (https://github.com/lsils/mockturtle) is a synthesis tool partially
integrated with LiveHD. The goal of this task is to iron out bugs and issues
and to use the LiveHD Tasks API to parallelize the synthesis.

Main features:

* The current synthesis divides the circuit in partitions. Each partition can be synthesized in parallel.
* Support hierarchical synthesis to optimize cross Lgraphs (cross verilog module optimization)

The goal is to use Mockturtle (https://github.com/lsils/mockturtle) with LiveHD. The main characteristics:

* Use mockturtle to tmap to LUTs
* Use mockturtle to synthesize (optimize) logic
* Enable cut-rewrite as an option
* Enable hierarchy cross optimization (hier:true option)
* Use the graph labeling to find cluster to optimize
* Re-timing
* Map to LUTs only gates and non-wide arithmetic. E.g: 32bit add is not mapped to LUTS, but a 2-bit add is mapped.
* List of resources to not map:
    * Large ALUs. Large ALUs should have an OpenWare block (hardcoded in FPGAs and advanced adder options in ASIC)
    * Multipliers and dividers
    * Barrell shifters with not trivial shifts (1-2 bits) selectable at run-time
    * memories, luts

### LiveHD Console

|   |   |
|---|---|
| Title | LiveHD Console |
| Description | Create a console app that interacts with LiveHD to query parameters about designs |
| Mentor(s) | Jose Renau|
| Skills | C++17 |
| Difficulty | Medium |
| Size | Medium 175 hours|
| [Link](https://github.com/masc-ucsc/livehd/blob/master/docs/projects_small.md#medium-query-shell-not-lgshell-to-query-graphs)


Current LiveHD uses replxx but it a no longer maintained shell/console. The result is that it fails in newer versions of OSX.

There is an alternative Crossline (https://github.com/jcwangxp/Crossline). This affects main/main.cpp and nothing else.

In addition to replace the current console with auto-completion, the plan is to add "query" capacity to visualize some
of the LiveHD internals.


* Query bits, ports...  like
    * https://github.com/rubund/netlist-analyzer
    * https://www.jameswhanlon.com/querying-logical-paths-in-a-verilog-design.html
* It would be cool if subsections (selected) parts can be visualized with something like https://github.com/nturley/netlistsvg
* The shell may be expanded to support simulation in the future
* Wavedrom/Duh dumps

Wavedrom and duh allows to dump bitfield information for structures. It would be interesting to explore to dump tables and bit
fields for Lgraph IOs, and structs/fields inside the module. It may be a way to integrate with the documentation generation.

Example of queries: show path, show driver/sink of, do topo traversal,....


### Compiler error generation pass

|   |   |
|---|---|
| Title | Lgraph and LNAST check pass |
| Description | Create a pass that check the integrity/correctness of Lgraph and LNAST |
| Mentor(s) | Jose Renau|
| Skills | C++17 |
| Difficulty | Medium |
| Size | Large 350 hours|
| [Link](https://github.com/masc-ucsc/livehd/blob/master/docs/projects_small.md#medium-diagnostics )

Create a pass that checks that the Lgraph (and/or LNAST) is semantically
correct. The LNAST already has quite a few tests (pass.semantic), but it can be
further expanded. Some checks:

* No combinational loops
* No mismatch in bit widths
* No disconnected nodes
* Check for inefficient splits (do not split buses that can be combined)
* Transformations stages should not drop names if same net is preserved
* No writes in LNAST that are never read
* All the edges are possible. E.g: no pin 'C' in Sum_op

