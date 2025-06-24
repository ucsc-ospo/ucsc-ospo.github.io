---
title: "Writing a blog about your OSRE 2025 project"
subtitle: "Since OSRE 2023 we ask student contributors to blog!"
summary: "This is now common practice and an efficient way to track activities within OSRE projects. Include links to proposals, presentations, reports, and experience."
authors: [slieggi, carlosm]
tags: [osre25]
categories: []
date: 2024-10-21
lastmod: 2025-05-13
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

OSRE participants are required to blog three times during their summer program. The first blog is a chance to introduce yourself and your project. The second blog occurs around the mid-point of the project and a final blog post is expected as part of you final project delverable. The organization administrator will send emails with specific dates. Instructions for the blog are indicated below. All blogs should include links to proposals, presentations, links to any deliverables/products as well as an overview of the student's experience. Check out the student pages from previous years to get an idea of content / size. 

We will also ask students and contributors to provide regular status updates which will help track your activities. The organization administrator will provide more details once the program work begins. 


## Making a pull request for your blog

- Fork the [git repository](https://github.com/ucsc-ospo/ucsc-ospo.github.io)
- If you haven't already done so, add your profile using [these instructions](/osredocs/formentors/#instructions-for-adding-a-mentor)
  - **IMPORTANT**: Under `user_groups:` add `- 2025 Contributors` (as opposed to any of the two mentor groups)
  - The short bio and any other information goes below the frontmatter

- Post your blog
  - Add `/content/report/osre25/ORGANIZATION/PROJECTNAME/DATE-USERNAME/index.md`
  - Add a frontmatter to `index.md`, using the labels below
  - Blog text goes below the frontmatter
  - In that same directory include a picture and call it `featured.png` (also supports `.jpg`, `.jpeg`) 
- Commit to your fork and make a pull request. [Email OSRE Admins](mailto:ospo-info-group@ucsc.edu/) with questions.

### Example frontmatter and text body
```
---
title: "YOUR TITLE"
subtitle: "YOUR SUBTITLE (OPTIONAL)"
summary:
authors: 
  - USERNAME1
  - USERNAME2
tags: ["osre25"]
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

As part of the [PROJECTNAME](/project/osre25/ORGANIZATION/PROJECTNAME) my [proposal](https://...) under the mentorship of MENTOR aims to ...
```
