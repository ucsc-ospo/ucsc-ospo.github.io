---
title: "Midterm Blogpost: HDEval's LLM Benchmarking for HDL Design"
subtitle: ""
summary:
authors: 
  - ashwinbardhwaj
tags: ["osre24", uc, reproducibility, LLM, HDL]
categories: []
date: 2024-07-18
lastmod: 2024-07-18
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---
## Introduction
Hello! My name is {{% mention ashwinbardhwaj %}}, an electrical engineering and computer science student based in San Diego, CA. For the past 6 weeks, I have been working closely with Professor {{% mention renau %}} on the [HDEval](https://github.com/masc-ucsc/hdeval) project. The aim of this project is to create mutiple project sized HDL benchmarks to evaluate how well existing LLMs can generate Verilog/Chisel code. These benchmarks will include my own "golden" HDL implementation of the project as well as respective English prompts to guide the LLM. I am excited to be able to work with these tools that have the potential to become a valuable resource for HDL design. So far, I have been successful in creating the first benchmark, a pipelined 3 stage RISC-V core, as well as working through by second project, a Gameboy Emulator. 


## RISC-V Implementation
Over this past month and a half, I have successfully completed my first benchmark which focuses on creating, modeling, and testing a pipelined 3-stage RISC-V core. The core uses the fetch, decode, and excute structure and is functional for most RV32I instructions. I synthesized and simulated my Verilog using Icarus Verilog and displayed the waveforms on GTKWave. After development, a good section of time was spent creating and tuning the English explanation of each Verilog module. After running these benchmark files through several LLM APIs, we compared the existing "golden" modules with the generated ones and noticed that more recent versions of LLMs such as GPT 4o and Claude 3 preform much better at creating synatically correct and efficent code. 

In addition, I have also created a tool that will parse the Verilog and instruction files into the necessary json structure to then test on various models.

## Gameboy Emulator
I am also in the process of developing the second benchmark, which targets a Gameboy emulator. This will challenge the LLMs much more than the RISC-V project because apart from the custom CISC CPU, the model should also understand how to handle various other blocks of the hardware system including memory, picture processing unit (PPU), sound processing unit (SPU), various input/output systems like the buttons and cartridge, and interupt handlers. As a result, it will challenge the model to understand the system as a whole when creating each individual module.


## Next Steps
As we continue on to the second half of the project, I will coninue working on my gameboy emulator. I have already completely developed and tested the Z80-esque CPU, DMA, and interrupt handler but need to continue working on the display and sound interfaces. Also, I will also continue to evaluate and run these tests over a wider range of LLMs to get a better picture of what models and versions are best suited for HDL design as well as the direction these models are going in.
