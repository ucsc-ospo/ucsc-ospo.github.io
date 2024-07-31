---
# Display name
title: Enhencing h5bench with HDF5 Compression Capability 

# Summary

summary:

# Username (this should match the folder name)
authors:
- henryz
- jeanlucabez

tags: [osre24, uc]
categories: ["GSoC'24"]
date: 2024-05-27
lastmod: 2024-7-31
featured: false
draft: false

image:
  caption: ""
  focal_point: ""
  preview_only: false
---

	As part of the [h5bench](/project/osre24/osu/h5bench) project my [Enhencing h5bench with HDF5 Compression Capability](https://summerofcode.withgoogle.com/myprojects/details/n0H28Z40) under the mentorship of Dr. {{% mention jeanlucabez %}} and Dr. Suren Byna aims to allow users of h5bench to incoporate compression features in their simulations by creating custom benchmarks with common scientific lossless&lossy compression algorithms such as SZ, SZ3, ZFP, and GZIP.    

	The problem I am trying to solve is to implement multiple data compression algorithms in h5bench core access patterns through HDF5 filters. This capability should grant users the flexibility to configure the parameters and methods of compression applied to their datasets according to their specific needs and preferences. My solution primarily involves using a user-defined HDF5 filter mechanism to implement lossless and lossy compression algorithms, such as ZFP, SZ, and cuSZ. Throughout the process, I will deliver one C source code implementing compression configuration settings, one C source code implementing lossless and lossy algorithms, a set of performance reports before and after data compression in CSV and standard output files, and a technical documentation on h5bench user manual website.

# Midterm Blog
	This summer, after completing my junior year, I was honored to have the opportunity working with Dr. Jean Luca Bez and Dr. Suren Byna on the h5bench, an open-source benchmarking project designed to simulate runnning sync/async HDF5 I/O on HPC machines. This post will cover mostly what I have learned, produced, planned, and thoughts over the first six weeks.

	First of all, let's define some of the terms here. HDF5 stands for Hierarchical Data Format 5. Unlike other data storage formats (JSON, CSV, XML...), HDF5 is not only a container that manages data similar to a file system, but also a powerful library that gives you the ability to perform I/O (Inputs/Outputs) operations between memory and file. One of the reasons this tool is commonly used by HPC applications is that it also supports MPI I/O, which is a protocol for parallel computing (you can think of it as the parallel version of POSIX). With exabytes of data and high frequencies of usage for analysis in scientific studies, HDF5 is perfect for the job. Essentially, h5bench is a software that tests the hardware's performance through HDF5 (it also provides other benchmark kernels such as AMReX, E3SM-IO, MACSio, and openPMD-api, but my job focuses on using vanilla HDF5 I/O).

	So, what I have done so far? Frist, my job is to allow users to tune input parameters regarding data compression, and make sure h5bench prints accurate benchmark results with the intended compression algorithm applied to their datasets. h5bench's frondend is written in Python, which takes an input of a JSON file from user and parses it into a CFG configuration file that can be read by the backend later, which is written in C. I created a new enum struct and made user able to specify one from a range of compression algorithms (SZ3, ZFP, LZ4, GZIP, and other pre-defined algorithms). I also made it possible to apply these algorithms to the datasets, so the .h5 (an HDF5 file) would contain chunks of compressed data after multiple H5Dwrite calls.

	Next, the challenges and gains. Throughout the first six weeks, 30% of the time was spent on understanding the newest version of h5bench and HDF5 by reading through C source codes and documentations, and asking many dumb questions to my mentors (thanks to their patience and great answers :D). Writing code is fairly easy after I really understood what the program is doing. By that I mean you have to understand every line in almost all functions and how each and every variables change. 40% of the time was used on debugging and testing the compression algorithm, mainly SZ3. To make code behaves correctly is another level of difficulty. Most of the issues resulted from failing to configure the application and dependent libraries correctly. Without necessary macros enabled during the build process, features like compression filter plugin will not run. As I was also new to CMake and HPC environment, I learned that new envrionment variables will be reset for every new session, even if you requested a compute node resource. Besides getting used to the standard build sequence: "cmake ..", "make", "make install", I also learned to use "ccmake .." to examine the flags of the compiled program. The rest of time I learned more about parallel computing, HDF5, compression algorithms, by reading some papers and documentations. A lot of notes were taken (I must say a good note taking system is the game changer). Last but not the least, I also spent times synchronizing online and offline with my mentors to discuess problems. Without their help, I can never make this far.

	My next phase will tackle these problems, here I am just offering a list:
	- Test applying filter with other compression algorithms, and with different dimension layout of the dataset
	- Add decompression capability
	- Allow users to tune the auxiliary parameters for controlling the behavior of a certain compression filter H5Pset_filter(COMPRESS_INFO.dcpl_id, H5Z_FILTER_SZ3, H5Z_FLAG_MANDATORY, 0, NULL); cd_nelmts cd_values[]
	- Print additional benchmark results to indicate what and how the compression filter is applied, and the compression ratio

