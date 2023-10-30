---
title: "Writing a blog about your OSRE 2024 project"
subtitle: "Since OSRE 2023 we ask student contributors to blog!"
summary: "This is now common practice and an efficient way to track activities within OSRE projects. Include links to proposals, presentations, reports, and experience."
authors: [slieggi, carlosm]
tags: [osre24]
categories: []
date: 2023-10-06
lastmod: 2023-10-07
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: [osre]
---

As last year, the Organization Admins will be asking students and contributors to provide regular status updates which will help us better highlight the work you are doing and track activities within our OSRE projects. These progress reports will also form the basis of blog reports prepared by students in the course of their summer. Blog reports should include links to proposals, presentations, reports, and an overview of the student's experience. 

Your experience is invaluable for future OSRE candidates and for improving the program every year.

## Size and content

Keep it short and crisp. Include a short description of your project, a link to your project proposal, and, later in the program, links to the GSoC reports you provided. 

## Making a pull request for your blog

- Fork the [git repository](https://github.com/ucsc-ospo/ucsc-ospo.github.io)
- If you haven't already done so, add your profile using [these instructions](/osredocs/formentors/#instructions-for-adding-a-mentor)
  - **IMPORTANT**: Under `user_groups:` add `- 2024 Contributors` (as opposed to any of the two mentor groups)
  - The short bio and any other information goes below the frontmatter

- Post your blog
  - Add `/content/report/osre24/ORGANIZATION/PROJECTNAME/DATE-USERNAME/index.md`
  - Add a frontmatter to `index.md`, using the labels below
  - Blog text goes below the frontmatter
  - In that same directory include a picture and call it `featured.png` (also supports `.jpg`, `.jpeg`) 
- Commit to your fork and make a pull request and [email OSRE Admins](mailto:ospo-info-group@ucsc.edu/) (currently: Stephanie Lieggi, Carlos Maltzahn).

### Example frontmatter and text body
```
---
title: "YOUR TITLE"
subtitle: "YOUR SUBTITLE (OPTIONAL)"
summary:
authors: 
  - USERNAME1
  - USERNAME2
tags: ["osre24"]
categories: []
date: YYYY-MM-DD
lastmod: YYYY-MM-DD
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

As part of the [PROJECTNAME](/project/osre24/ORGANIZATION/PROJECTNAME) my [proposal](https://...) under the mentorship of MENTOR aims to ...
```