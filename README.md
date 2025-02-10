# The Open Source Program Office, UC Santa Cruz

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![twitter](https://img.shields.io/twitter/follow/UC_OSPO?style=social)](https://twitter.com/UC_OSPO)

## How to add a new project idea to the Open Source Research Experience

### Instructions for adding/updating a project

A project serves as the context for one or more project ideas. Each project is represented as a web page with project information and ideas. Projects and their updates are subject to review of the OSRE administrators. 

- Option A: email OSRE [administrators](mailto:slieggi@ucsc.edu) 
- Option B (via git):
  - Fork [git repository](https://github.com/ucsc-ospo/ucsc-ospo.github.io)
  - Create `content/project/osre25/ORGANIZATION/PROJECTNAME` directory or copy it from previous year's `content/project/osre24/ORGANIZATION/PROJECTNAME`
  - In that directory create/update `index.md` and the project's image (`featured.png` or `featured.jpg`) 
  - In `index.md` fill in the frontmatter (see [example](https://raw.githubusercontent.com/ucsc-ospo/ucsc-ospo.github.io/main/content/project/osre22/ucsc/polyphorm/index.md)):
    - Add the project's title in `title:`, 
    - Date the project entry with `date:` and `lastmod:`, using the format `2022-05-27`. **Note that projects dated in the future will not display**.
    - Include a list of `authors:`, using either names in quotes or user names (see below for instructions on how to establish user names)
    - **IMPORTANT**: set a list of tags that include `"osre25"` and either `"uc"` or `"reproducibility"` or both, depending on whether your project has a mentor affiliated with a UC campus or associated national lab (LBL, LANL, LLNL), or is a _Summer of Reproducibility_ project. Feel free to add additional tags.
    - Below the frontmatter start with a description of the project and include links to the project's webpage. 
    - Add each project idea with level-3 header, i.e., `### ...` and add a list of **essential information** that includes *topics*, *skills*, *difficulty*, *size* (175 vs 350 hours), and *mentors*.
  - Make a pull request.
  
### Instructions for adding a mentor

Mentors are welcome to add information about themselves (see [example](https://ospo.ucsc.edu/author/stephanie-lieggi/)): 
- Option A: email OSRE [administrators](mailto:slieggi@ucsc.edu) 
  - Include name, title, affiliations, email, short bio, github profile (if applicable), whether you are UC or Summer of Reproducibility mentor (or both), and, optionally, photo, web page and social media links.
- Option B (via git): 
  - Fork [git repository](https://github.com/ucsc-ospo/ucsc-ospo.github.io) (or combine with pull request of adding/updating a project above)
  - Create `/content/authors/USER` directory (where `USER` is a unique username, e.g. the one you use for your github account).
  - In that directory copy an `_index.md` file from another user and update it (see [example](https://raw.githubusercontent.com/ucsc-ospo/ucsc-ospo.github.io/main/content/authors/slieggi/_index.md))
    - Many icons are available (see [documentation](https://bootstrap.hugoblox.com/getting-started/page-builder/#icons))
    - **IMPORTANT**: Under `user_groups:` add either `- University of California Mentors` or `- Summer of Reproducibility Mentors` (or both).
    - The bio and any other information goes below the frontmatter.

## Posts, Projects, Authors, Reports, Events

The website has five "lists": 
- **Posts:** (under `content/post`) include Programs (`category: programs`) named after their program name, and the OSPO Blog items (`category: news`) named after their posting date (`yyyymmdd`) with tags that determine whether news items are also appearing in OSRE News (tag `osre`) and SoR News (tag `sor`).
- **Projects:** (under `content/project`) are filed in a directory hierarchy with year at the top (e.g. `osre22`, `osre23`) and organization for each year. This directory hierarchy avoids name collisions of project names between years and organizations but the website build process does not assign any further meaning to it. Instead, tags determine in which year a project shows up (e.g. tag `osre22` or `osre23`) and whether the project is a UC mentor project (tag `uc`) or a reproducibility project (tag `reproducibility`) or both. Additional tags describing project topics are encouraged and show up in the OSRE tag cloud (across all years and organizations).
- **Authors** (under `content/authors`) include administrators and OSRE mentors. There are three `user_groups`: `Administration`, `University of California Mentors`, and `Summer of Reproducibility Mentors`. Authors can belong to more than one group.
- **Reports:** (under `content/report`) are authored by OSRE contributors and will appear in the ["Student Pages" section on the OSRE page](https://ospo.ucsc.edu/osre/#studentpages).
- **Events:** (under `content/event`) lists the annual symposia (and possibly additional major events). The `content/event/_index.md` is showing the upcoming event (or the past event if there is no upcoming event yet) and a call-to-action button to register (or to watch the recording of the past event). The list items are past events named by their event date.

## How to add a new annual edition of the Open Source Research Experience

To archive the current year (e.g. 2024) and start a new OSRE edition: 
- Update `/content/osre/index.md`
- Copy `/content/osre24` to `/content/osre25` 
- Make the following updates within `/content/osre25`:
  - Update `/content/osre25/intro.md`
  - Rename and update `content/osre25/osre25.md`
  - For Student Pages:
    - In `/content/osre25/studentpages.md` 
      - Update `subtitle: "Go to [2024 student pages](/osre24/#studentpages)"`
      - Update `tag: [osre25]`
      - Update "OSRE 2025" in body
    - In `/content/osre24/studentpages.md` update `subtitle: "Go to [2023 student pages](/osre23/#studentpages)  \nReturn to [2025 student pages](/osre25/#studentpages)"`
  - For Projects:
    - In `/content/osre25/projects.md` 
      - Update `title: 2025 Projects`
      - Update `subtitle: "Go to [2024 projects](/osre24/#projects)"`
      - Update `tag: [osre25]`
    - In `/content/osre24/projects.md"` update `subtitle: "Go to [2023 projects](/osre23/#projects)  \nReturn to [2025 projects](/content/osre25/#projects)"`
  - For Timelines:
    - In `/content/osre25/timeline.md` 
      - Update `subtitle: "Go to [2024 timeline](/osre24/#timeline)"`
      - In body update `caption="Table: OSRE 2025 Timeline"`
      - Update `/content/osre25/timeline.csv`
    - In `/content/osre24/timeline.md` update `subtitle: "Go to [2023 timeline](/osre23/#timeline)  \nReturn to [2025 timeline](/osre25/#timeline)"`
- Copy `/content/report/osre24/ucsc/admin/20231006-admin` to `/content/report/osre25/ucsc/admin/20231021-admin` (or any other `YYYYMMDD-admin` name) and update tags (and any new instructions) in `index.md` of that directory:
  - Update title to OSRE 2025
  - Replace all `osre24` with `osre25`
- Update `/content/osre25/intro.md` cta link `url: '/osre25/#projects'`
- Update `/content/osredocs` files for mentors, students, and mentor FAQs for OSRE 2025 (The OSRE documentation is updated in place -- use version control to find out about documentation of earlier years)
- Copy `/content/sor24` to `/content/sor25`, make 2025 updates to `/content/sor25`, and update SoR links in `/content/oser25/osre25.md` to `/sor25` and vice versa.

## How to fix the deployment workflow

Upon merging a pull request, the website uses a GitHub workflow to first build the new version of the website and then deploy it on GitHub Pages. The workflow is specified in `.github/workflows/hugo.yaml`. It is based on the [recommended workflow for Hugo sites](https://github.com/actions/starter-workflows/blob/main/pages/hugo.yml) but with differences that are necessary for older Hugo versions (see below). Every once in a while GitHub decides to introduce breaking changes to the meaning of their workflow commands. This usually requires no more than changing the versions to the latest shown in the [sample workflow](https://github.com/actions/starter-workflows/blob/main/pages/hugo.yml). A good example is the combined update of pull requests [#726](https://github.com/ucsc-ospo/ucsc-ospo.github.io/pull/726) and [#727](https://github.com/ucsc-ospo/ucsc-ospo.github.io/pull/727).

## Website framework

This website is based on [Hugo Blox](https://hugoblox.com), a website framework using [Hugo](https://github.com/gohugoio/hugo) that can be deployed with GitHub and Netlify. The theme of the OSPO website is the [Research Group Theme](https://research-group.netlify.app/).  

**Important:** The website is using a Bootstrap-styled version of a Hugo Blox template. Therefore, the [Bootstrap documentation site](https://bootstrap.hugoblox.com/) is relevant here. New templates are now Tailwind-styled. This website tends to throw errors with Hugo versions greater than `0.119.0` -- possibly due to lack of maintenance of its Bootstrap-styled template.
