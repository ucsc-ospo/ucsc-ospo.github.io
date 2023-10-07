# The Open Source Program Office, UC Santa Cruz

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![twitter](https://img.shields.io/twitter/follow/UC_OSPO?style=social)](https://twitter.com/UC_OSPO)

## How to add a new project idea to the Open Source Research Experience

### Instructions for adding/updating a project

A project serves as the context for one or more project ideas. Each project is represented as a web page with project information and ideas. Projects and their updates are subject to review of the OSRE administrators. 

- Option A: email OSRE [administrators](mailto:slieggi@ucsc.edu) (currently: Stephanie Lieggi, Carlos Maltzahn)
- Option B (via git):
  - Fork [git repository](https://github.com/ucsc-ospo/ucsc-ospo.github.io)
  - Create `content/project/osre23/ORGANIZATION/PROJECTNAME` directory or copy it from previous year's `content/project/osre22/ORGANIZATION/PROJECTNAME`
  - In that directory create/update `index.md` and the project's image (`featured.png` or `featured.jpg`) 
  - In `index.md` fill in the frontmatter (see [example](https://raw.githubusercontent.com/ucsc-ospo/ucsc-ospo.github.io/main/content/project/osre22/ucsc/polyphorm/index.md)):
    - Add the project's title in `title:`, 
    - Date the project entry with `date:` and `lastmod:`, using one of the formats `2022-05-27` (day only), `2022-05-27T07:32:00` (with time), `1979-05-27T00:32:00-07:00` (UTC-7 timezone), or `2022-05-27T07:32:00Z` (UTC timezone). Note that projects dated in the future will not display.
    - Include a list of `authors:`, using either names in quotes or user names (see below for instructions on how to add user names)
    - **IMPORTANT**: set a list of tags that include `"osre23"` and either `"uc"` or `"reproducibility"` or both, depending on whether your project has a mentor affiliated with a UC campus or associated national lab (LBL, LANL, LLNL), or is a _Summer of Reproducibility_ project. Feel free to add additional tags.
    - Below the frontmatter start with a description of the project and include links to the project's webpage. 
    - Add each project idea with level-3 header, i.e., `### ...` and add a list of **essential information** that includes *topics*, *skills*, *difficulty*, *size* (175 vs 350 hours), and *mentors*.
  - Make a pull request.
  
### Instructions for adding a mentor

Mentors are welcome to add information about themselves (see [example](https://ospo.ucsc.edu/author/stephanie-lieggi/)): 
- Option A: email OSRE [administrators](mailto:slieggi@ucsc.edu) (currently: Stephanie Lieggi, Carlos Maltzahn)
  - Include name, title, affiliations, email, short bio, whether you are UC or Summer of Reproducibility mentor (or both), and, optionally, photo, web page and social media links.
- Option B (via git): 
  - Fork [git repository](https://github.com/ucsc-ospo/ucsc-ospo.github.io) (or combine with pull request of adding/updating a project above)
  - Create `/content/authors/USER` directory.
  - In that directory copy an `_index.md` file from another user and update it (see [example](https://raw.githubusercontent.com/ucsc-ospo/ucsc-ospo.github.io/main/content/authors/slieggi/_index.md))
    - Many icons are available (see [documentation](https://wowchemy.com/docs/getting-started/page-builder/#icons))
    - **IMPORTANT**: Under `user_groups:` add either `- University of California Mentors` or `- Summer of Reproducibility Mentors` (or both).
    - The bio and any other information goes below the frontmatter.

## Posts, Projects, Authors, Reports, Events

The website has five "lists": 
- **Posts:** (under `content/post`) include Programs (`category: programs`) named after their program name, and the OSPO Blog items (`category: news`) named after their posting date (`yyyymmdd`) with tags that determine whether news items are also appearing in OSRE News (tag `osre`) and SoR News (tag `sor`).
- **Projects:** (under `content/project`) are filed in a directory hierarchy with year at the top (e.g. `osre22`, `osre23`) and organization for each year. This directory hierarchy avoids name collisions of project names between years and organizations but the website build process does not assign any further meaning to it. Instead, tags determine in which year a project shows up (e.g. tag `osre22` or `osre23`) and whether the project is a UC mentor project (tag `uc`) or a reprodubility project (tag `reproducibility`) or both. Additional tags describing project topics are encouraged and show up in the OSRE tag cloud (across all years and organizations).
- **Authors** (under `content/authors`) include administrators and OSRE mentors. There are three `user_groups`: `Administration`, `University of California Mentors`, and `Summer of Reproducibility Mentors`. Authors can belong to more than one group.
- **Reports:** (under `content/report`) are authored by OSRE contributors and will appear in the ["Student Pages" section on the OSRE page](https://ospo.ucsc.edu/osre/#studentpages).
- **Events:** (under `content/event`) lists the annual symposia (and possibly additioinal major events). The `content/event/_index.md` is showing the upcoming event (or the past event if there is no upcoming event yet) and a call-to-action button to register (or to watch the recording of the past event). The list items are past events named by their event date.

## How to add a new annual edition of the Open Source Research Expserience

To archive the current year (e.g. 2023) and start a new OSRE edition: 
- Copy `/content/osre` to `/content/osre23` (`/content/osre` contains always the newest edition, `/content/osre23` is the archived edition)
- Update tags in `content/osre` projects and reports lists:
  - In `content/osre/studentpages.md` update `tag: [osre24]`
  - In `content/osre/projects.md` update `tag: [osre24]`
- Update links to previous year and back to new year
  - For Student Pages:
    - In `/content/osre/studentpages.md` update `subtitle: "Go to [last year's student pages](/osre23/#studentpages)"`
    - In `/content/osre23/studentpages.md` update `subtitle: "Return to [new student pages](/osre/#studentpages)"`
  - For Projects:
    - In `/content/osre/projects.md` update `subtitle: "Go to [last year's projects](/osre23/#projects)"`
    - In `/content/osre23/projects.md` update `subtitle: "Go to [2022 projects](/lastosre) or return to [new projects](/osre/#projects)"` (2022 projects are under `/lastosre` because that was still under CROSS. When archiving OSRE 2024, update `/content/osre24/projecs.md` with `subtitle: "Go to [2023 projects](/osre23/#projects) or return to [new projects](/osre/#projects)"`)
  - For Timelines:
    - In `/content/osre/timeline.md` update `subtitle: "Go to [last year's timeline](/osre23/#timeline)"`
    - In `/content/osre23/timeline.md` update `subtitle: "Return to [new timeline](/osre/#timeline)"`
- Copy `/content/report/osre23/ucsc/admin/20221106-admin` to `/content/report/osre24/ucsc/admin/20231006-admin` and update tags in `index.md` of that directory:
  - Update title to OSRE 2024
  - Replace all `osre23` with `osre24`
- Update `/content/osredocs` files for mentors, students, and mentor FAQs for OSRE 2024.

## Website framework

This website is based on [Wowchemy](https://wowchemy.com), a website framework using [Hugo](https://github.com/gohugoio/hugo) that can be deployed with GitHub and Netlify. The theme of the OSPO website is the [Research Group Theme](https://research-group.netlify.app/).
