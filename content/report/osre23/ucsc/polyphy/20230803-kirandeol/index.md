---
title: "Midpoint Blog Interactive Exploration of High-dimensional Datasets with PolyPhy and Polyglot"
subtitle: "Enhancing Data Interactivty of PolyPhy"
summary: ""
authors: [kirandeol]
author_notes: ["An undergrad at the University of Alberta"]
tags: ["osre23", uc]
categories: [GSoC'23]
date: 2023-08-03
lastmod: 2023-08-03
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

The last few months of my GSoC project have been very exciting and I hope to share why with you here in this blog post! To briefly summarize, my project has been focused on further developing the Polyglot app, a tool for visualizing 3D language embeddings. One important part of Polyglot is its utilization of the novel MCPM metric, where points are colored according to their MCPM similarity to a user-chosen “anchor point” (e.g., if “hat” is our anchor point, then similar words like “cap” or “fedora” will be colored more prominently). 

The first issue we wanted to tackle was actually navigating the point cloud. With hundreds of thousands of points, it can be difficult to find what you’re looking for! Thus, the first few features added were a search bar for points and anchor points and a “jump to point” feature which changes a user’s center of rotation and “jumps” to a chosen point. There were a few hiccups with implementing these features, mainly due to the large number of points and the particular quirks of the graphics library Polyglot uses. In the end though, these simple features made it feel a lot easier to use Polyglot. 

The next set of features related to our desire to actually annotate the point cloud. Similar to how one might annotate a Google doc (ie., highlight a chunk of text and leave a comment), we wanted to set up something similar, but with points! Indeed, this led to the development of a cool brush tool for coloring points, named and commented annotations (up to 5), a search bar within annotations, and finally a button to export annotations and comments to a CSV.

The next few weeks are looking bright as we strive to finish the PolyPhy-Polyglot pipeline (a notebook for quickly formatting MCPM data from PolyPhy and getting it into Polyglot). We also hope to add a unique “timeline” feature in which users can analyze sections of the point cloud based on the associated time of each point. Overall, it’s been a very stimulating summer and I’m excited to push this project even further!
