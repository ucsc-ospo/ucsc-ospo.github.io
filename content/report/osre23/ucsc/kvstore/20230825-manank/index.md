
---
title: "KV store final Blog"
subtitle: ""
summary: ""
authors: [manank]
author_notes: ["Student at BITS Pilani"]
tags: ["osre23", uc]
categories: [GSoC'23]
date: 2023-08-25
lastmod: 2023-08-25
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

Hello again!
Before we get started, take a look at my previous blogs, [Introduction](/report/osre23/ucsc/kvstore/20230526-manank) and 
[Mid Term](/report/osre23/ucsc/kvstore/20230730-manank). The goal of the project was to implement io_uring based backend driver for client side, which was at 
that time using traditional sockets. The objective was improving performance from the zero copy capabilities of io uring. In the process, I learnt about many things, 
about [libkinetic](https://gitlab.com/kinetic-storage/libkinetic/-/tree/develop) and KV stores in general.

I started by writing a separate driver using io_uring in libkinetic/src in ktli_uring.c, most of which is similar to the sockets backend in ktli_sockets.c. The only
difference was in the send and receive functions. For more detailed description about the implementation, refer to the mid term blog.

After the implementation, it was time to put it to test. We ran extensive benchmarks with a tool called [fio](https://fio.readthedocs.io/en/latest/fio_doc.html), which
is generally used to run tests on filesystems and other IO related things. Thanks to Philip, who had already written an IO engine for testing kinetic KV store ([link](https://github.com/pkufeldt/fio)), I didn't have much problem in setting up the testbench. Again thanks to Philip, He set up a ubuntu server with the kinetic server
and gave me access through ssh. We ran extensive tests on that server, with both socket and uring backends, with several different block sizes. The link to the benchmarks sheet can be found [here](https://docs.google.com/spreadsheets/d/1HE7-KbxSqYZ3vmTZiJYoq21P7zfymU7N/edit?usp=sharing&ouid=116274960434137108384&rtpof=true&sd=true).

We spent a lot of time in reading and discussing the numbers, probably the most time consuming part of the project, we had several long discussions analyzing numbers
and their implications, for example in the initial tests, we were getting very high std dev in mean send times, then we figured it was because of the network 
bottleneck, as we were using large block sizes and filling up the 2.5G network bandwidth quickly.

In conclusion, we found out that there are many other major factors affecting the performance of the KV store, for example the network, and the server side of the KV
store. Thus, though io_uring offers performance benefit at the userspace-kernel level, in this case, there were other factors that had more significant effect than the
kernal IO stack on the client side. Thus, for increasing the performance, we need to look at the server side

I would like to thank Philip and Aldrin for their unwavering support and in depth discussions on the topic in our weekly meetings, I learned a lot from them 
throughout the entire duration of the project. 

