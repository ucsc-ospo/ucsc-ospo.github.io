---
title: How to add a new project idea to OSRE
summary: ''
authors: [admin, slieggi]
date: "2022-11-06T00:00:00Z"

reading_time: false  # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?

# Optional header image (relative to `assets/media/` folder).
#banner:
#  caption: ""
#  image: "bank.png"
---

# Instructions for adding a new project idea

- Option A: email OSRE [administrators](mailto:slieggi@ucsc.edu) (currently: Stephanie Lieggi, Carlos Maltzahn)
- Option B (via netlify CMS): 
- Option C (via git):
  - Fork [git repository](https://github.com/carlosmalt/ucsc-ospo)
  - Create `content/project/osre23/ORGANIZATION/PROJECTNAME` directory or copy it from previous year's `content/project/osre22/ORGANIZATION/PROJECTNAME`
  - In that directory create/update `index.md` and the project's image (`featured.png` or `featured.jpg`) 
  - In `index.md` fill in the frontmatter (between `---`s, see example):
    - Add the project's title in `title:`, 
    - Date the project entry with `date:` and `lastmod:` using [RFC 3339 date](https://github.com/toml-lang/toml#local-date-time).
    - Include a list of `authors:`. 
    - **IMPORTANT**: set `categories: ["osre23"]` and `tags:` with a list of tags that include either `"uc"` or `"reproducibility"` or both, depending on whether your project has a mentor affiliated with a UC campus or associated national lab (LBL, LANL, LLNL), or is a _Summer of Reproducibility_ project. Feel free to add additional tags.
    - Below the frontmatter start with a description of the project and include links to the project's webpage. 
    - Add each project idea with level-3 header, i.e., `### ...` and include a list consisting of topics, skills, difficulty, size, and mentors (see [example](github.com/carlosmalt/ucsc-ospo)).
  - Make a pull request and add [@carlosmalt](https://github.com/carlosmalt) and [@slieggi](https://github.com/slieggi).



