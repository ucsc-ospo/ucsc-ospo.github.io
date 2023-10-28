---
title: "These 4 new features will change the way you use OpenROAD"
subtitle: ""
summary: ""
authors: [luarss]
author_notes: ["Student at National University of Singapore"]
tags: ["osre23", uc, reproducibility]
categories: ["chip-design"]
date: 2023-07-27
lastmod: 2023-07-27
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

Welcome to the final blog post for my GSoC’23! Once again, my name is
Jack and I am working under the open-source electronic design automation
project - OpenROAD. We are a fast growing leading open-source 
foundational application for semiconductor digital design, as evidenced 
from our consistent star growth since inception. You may check us out 
at this [link](https://github.com/The-OpenROAD-Project/OpenROAD/). 
Allow me to share the four significant contributions I made in this GSoC 
project.

[![Star History Chart](https://api.star-history.com/svg?repos=The-OpenROAD-Project/OpenROAD&type=Date)](https://star-history.com/#The-OpenROAD-Project/OpenROAD&Date)

## 1) Improving Ease of Installation

Firstly, OpenROAD is now able to support multiple operating systems. 
This is essential as one of our primary goals is to democratise chip 
implementation. And installation is often one of the hardest steps 
to get right, so that was one of our priorities. Today, we have 
provided options for different types of installation:

- *Prebuilt binaries*: Local installations can often be riddled 
with incompatibilities or unexpected bugs, as well as taking a long 
compilation time. We sidestepped this by providing semi-regular 
updates to OpenROAD binary, reducing the time to installation.
- *Docker*: Echoing previous concerns, we also enabled Docker installation 
for 9 major operating systems. Docker is extremely flexible and runs 
on many operating systems (as long as it is supported by Docker).

With these changes, we have observed 10% reduction of installation related Github issues posted on a weekly basis. 

![Pic1](pic1.png "Figure 1: Supported OS matrix")

## 2) Filling Missing Documentation

Next, we have made considerable improvements to over 20 tool-specific
documentations, introducing consistent formatting styles for each page.
We introduce default values and datatypes to allow users to use the 
tools with greater ease.

![Pic2](pic2.png "Figure 2: Helpful documentation defaults and datatype")

Rather than having all arguments for a function under a common table,
we separated out into developer arguments and developer commands. 
This is to further make our documentation more beginner-friendly to read,
while not alienating our technical userbase. We have also added sections 
for example scripts and regression test, so as to help onboard 
newcomers to each tool of the flow.

![Pic3](pic3.png "Figure 3: Useful developer commands, example scripts, and regression test instructions")

## 3) Extensible Documentation Framework

Thirdly, we have introduced extensible documentation frameworks. 
Now, what do we mean by *extensible*? It means we have created an 
infrastructure which is easy to use for developers, and allows for 
greater maintanability. Our goal is to create something that 
requires minimal changes to add content for documentation. 

So, how did we do this?

We introduced 4 initiatives, namely: the warning/error messages glossary.
We noticed that people were searching for error and warning messages,
but our documentation did not have them. So we added a page where all 
the error/warning messages along with relevant code line number can
be generated automatically. On top of that, developers can add useful 
debug information to help the end user.

![Pic4](pic4.png "Figure 4: Warning/Error messages glossary.")

Next, we also introduced automatically generated Doxygen pages, which 
integrates nicely into our C++/Tcl source code framework. This automatic 
generation will make it much more convenient for developers to just 
insert comments into their source code, and allow Doxygen to generate 
documentation automatically.

![Pic5](pic5.png "Figure 5: Doxygen pages.")

Next, we introduced cloud-based packaging. It is important that our 
framework is able to runnable on cloud, and the ever-popular notebook 
format. Our Colab based notebook was created with this in mind, and 
allows for easy transfer to other notebook providers with some 
modifications. Check out the notebooks here!

![Pic6](pic6.png "Figure 6: Google Colab can now run OpenROAD scripts.")

Lastly, we have the changelog workflow which can be triggered manually.
For our open-source project, we have chosen not to do software releases. 
This means it can be difficult to track the changes between commit 
numbers. Adding this workflow can help newcomers track the changes 
easier, by month.

![Pic7](pic7.png "Figure 7: Sample output of github changelog")

## 4) OpenROAD Chatbot

Finally, we are also discussing the potential of creating a chatbot whose
purpose is to answer user queries. We were thinking, there are lots of 
domain knowledge in Slack Channels, Github repos, and so on, so why 
not create a LLM-based chatbot. Stay tuned for updates!

## Personal Reflections

To me, my most valuable takeaway is with regards to code quality. Often
times, we as coders tend to opt for the best solution and “hack” something 
out quickly. Hacking is fine, as a proof of concept - but not for 
long term code development. Working in open-source projects like this, 
I have learnt to avoid creating unnecessary files, shortening the code 
and optimising runtime. In doing our job, we also wish to make life 
easier, not harder for future developers

## Final Words

I would like to express my gratitude to my mentors Indira and Vitor for
their guidance and insight throughout the project, as well as the 
OpenROAD dev team for their assistance. Would also like to thank the 
Google Summer of Code organising committee, and UCSC for creating such a 
wonderful program. Being able to contribute to actual real open-source 
projects with real needs, is truly the best of both worlds for aspiring 
programmers.
