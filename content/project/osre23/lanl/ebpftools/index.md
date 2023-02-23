---
title: "eBPF Monitoring Tools"
authors: ["Gary Grider"]
author_notes: ["High Performance Division Leader, Los Alamos National Laboratory"]
tags: ["osre23", "uc", "performance", "operating systems"]
date: 2023-02-21
lastmod: 2023-02-22
---

[eBPF](https://ebpf.io) is a technology that allows sandboxed programs to run in a priviledged context such as a Linux kernel. eBPF is for operating systems what Javascript is for web browsers: new functionality can be safely loaded without restarting or continually upgrading the operating system or browser and executed efficiently. eBPF is used to introduce new functionality into a running Linux kernel, including next-generation networking, observability, and security functionality. The following is just one idea of many possible.

### Implement Darshan functionality as eBPF tool

- **Topics:** performance, I/O, workload characterization
- **Difficulty:** Medium
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** [Mentor Name #1](mailto:mentor@example.com), [Mentor Name #2](mailto:mentor@example.com)

[Darshan](https://www.mcs.anl.gov/research/projects/darshan/) is an HPC I/O characterization tool that collect statistics using a lightweight design that makes it suitable for full time deployment. Darshan is an interposer library that catches and counts IO requests (open, write, read, etc.) to a file/file system and it keeps the counters in buckets in data structure that can be queried.  How many reads of small size, medium size, large size) for example are the types of things that are counted.

Having this be an interposer library requires users to link their application with this library.  Having this function in epbf would make this same function transparent to users.  Darshan has all the functions and could provide the list of functions to implement and the programmer could build and test these functions in ebpf on a linux machine.  This could be a broadly available open tool that would be generally useful and but one of perhaps hundreds of examples of where ebpf based tools that could be in the open community for all to leverage.
