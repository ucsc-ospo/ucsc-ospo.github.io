---
title: How to add a new project idea to OSRE
summary: ''
authors: [carlosm,slieggi]
date: "2024-02-07"

reading_time: false # Show estimated reading time?
share: false  # Show social sharing links?
profile: false  # Show author profile?
comments: false  # Show comments?
editable: true

# Optional header image (relative to `assets/media/` folder).
#banner:
#  caption: ""
#  image: "bank.png"
---

### Instructions for adding/updating a project

A project serves as the context for one or more project ideas. Each project is represented as a web page with project information and ideas. Projects and their updates are subject to review of the OSRE administrators. 

- Preferred method (via git):
  - Fork [git repository](https://github.com/ucsc-ospo/ucsc-ospo.github.io)
  - Create `content/project/osre26/ORGANIZATION/PROJECTNAME` directory or copy it from previous year's `content/project/osre25/ORGANIZATION/PROJECTNAME`
  - In that directory create/update `index.md` and the project's image (`featured.png` or `featured.jpg`) 
  - In `index.md` fill in the frontmatter (see [example](https://raw.githubusercontent.com/ucsc-ospo/ucsc-ospo.github.io/main/content/project/osre22/ucsc/polyphorm/index.md)):
    - Add the project's title in `title:`, 
    - Date the project entry with `date:` and `lastmod:`, using the format YYYY-MM-DD, e.g. `2026-05-27`. Note that projects dated in the future will not display.
    - Include a list of `authors:`, using either names in quotes or user names (see below for instructions on how to add user names)
    - **IMPORTANT**: set a list of tags that include `"osre26"`. Feel free to add additional tags.
    - Below the frontmatter start with a description of the project and include links to the project's webpage. 
    - Add each project idea with level-3 header, i.e., `### ...` and add a list of **essential information** that includes *topics*, *skills*, *difficulty*, *size* (175 vs 350 hours), and *mentors*.
    - Every mentor should at least have a `mailto:` link. Better yet: add the mentor using the instructions below and use the shortcut `{{%/* mention "USERNAME" */%}}`. There should be at least two mentors per project idea.
  - Make a pull request and [email OSRE Admins](mailto:ospo-info-group@ucsc.edu) (currently: Stephanie Lieggi).

*If you are unable to upload via git please [email OSRE Admins](mailto:ospo-info-group@ucsc.edu) (currently: Stephanie Lieggi) for other options*
  
### Instructions for adding a mentor

Mentors are welcome to add information about themselves (see [example](https://ospo.ucsc.edu/author/stephanie-lieggi/)): 

- Preferred methond (via git): 
  - Fork [git repository](https://github.com/ucsc-ospo/ucsc-ospo.github.io) (or combine with pull request of adding/updating a project above)
  - Create `/content/authors/USERNAME` directory.
  - In that directory copy an `_index.md` file from another user and update it (see [example](https://raw.githubusercontent.com/ucsc-ospo/ucsc-ospo.github.io/main/content/authors/slieggi/_index.md))
    - Many icons are available (see [documentation](https://wowchemy.com/docs/getting-started/page-builder/#icons))
    - **IMPORTANT**: Under `user_groups:` add `- University of California Mentors`.
    - The short bio and any other information goes below the frontmatter.
  - Make a pull request and [email OSRE Admins](mailto:ospo-info-group@ucsc.edu)
 
- Or [email OSRE Admins](mailto:ospo-info-group@ucsc.edu)
  - Include name, title, affiliations, email, short bio, whether you are UC or Summer of Reproducibility mentor (or both), and, optionally, photo, web page and social media links.

