
---
title: "Efficient Communication with Key/Value Storage Devices"
subtitle: ""
summary: ""
authors: [manank]
author_notes: ["Student at BITS Pilani"]
tags: ["osre23", uc]
categories: [GSoC'23]
date: 2023-05-26
lastmod: 2023-05-26
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

Hi everyone! 

I'm Manank Patel, and am currently an undergraduate student at Birla Institute of Technology and Sciences - Pilani, KK Birla Goa Campus. As part of the [Efficient Communication with Key/Value Storage Devices](/project/osre23/ucsc/kvstore) my [proposal](https://drive.google.com/file/d/1iJIlHuCpnvDeOyr5DphDDimqdl9s4hKH/view?usp=sharing) under the mentorship of {{% mention drin %}} and **Philip Kufeldt** aims to implement io_uring based communication backend for network based key-value store.

io_uring offers a new kernel interface that can improve performance and avoid the overhead of system calls and zero copy network transmission capabilities. The KV store clients utilize traditional network sockets and POSIX APIs for their communication with the KV store. A notable advancement that has emerged in the past two years is the introduction of a new kernel interface known as io_uring, which can be utilized instead of the POSIX API. This fresh interface employs shared memory queues to facilitate communication between the kernel and user, enabling data transfer without the need for system calls and promoting zero copy transfer of data. By circumventing the overhead associated with system calls, this approach has the potential to enhance performance significantly.

