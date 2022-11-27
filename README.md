# The Open Source Program Office, UC Santa Cruz

## How to add a new project idea to the Open Source Research Experience

### Instructions for adding/updating a project

A project serves as the context for one or more project ideas. Each project is represented as a web page with project information and ideas. Projects and their updates are subject to review of the OSRE administrators. 

- Option A: email OSRE [administrators](mailto:slieggi@ucsc.edu) (currently: Stephanie Lieggi, Carlos Maltzahn)
- Option B (via git):
  - Fork [git repository](https://github.com/carlosmalt/ucsc-ospo)
  - Create `content/project/osre23/ORGANIZATION/PROJECTNAME` directory or copy it from previous year's `content/project/osre22/ORGANIZATION/PROJECTNAME`
  - In that directory create/update `index.md` and the project's image (`featured.png` or `featured.jpg`) 
  - In `index.md` fill in the frontmatter (see [example](https://raw.githubusercontent.com/carlosmalt/ucsc-ospo/main/content/project/osre22/ucsc/polyphorm/index.md)):
    - Add the project's title in `title:`, 
    - Date the project entry with `date:` and `lastmod:`, using one of the formats `2022-05-27` (day only), `2022-05-27T07:32:00` (with time), `1979-05-27T00:32:00-07:00` (UTC-7 timezone), or `2022-05-27T07:32:00Z` (UTC timezone). Note that projects dated in the future will not display.
    - Include a list of `authors:`, using either names in quotes or user names (see below for instructions on how to add user names)
    - **IMPORTANT**: set a list of tags that include `"osre23"` and either `"uc"` or `"reproducibility"` or both, depending on whether your project has a mentor affiliated with a UC campus or associated national lab (LBL, LANL, LLNL), or is a _Summer of Reproducibility_ project. Feel free to add additional tags.
    - Below the frontmatter start with a description of the project and include links to the project's webpage. 
    - Add each project idea with level-3 header, i.e., `### ...` and add a list of **essential information** that includes *topics*, *skills*, *difficulty*, *size* (175 vs 350 hours), and *mentors*.
  - Make a pull request and add [@carlosmalt](https://github.com/carlosmalt) and [@slieggi](https://github.com/slieggi) as reviewers.
  
### Instructions for adding a mentor

Mentors are welcome to add information about themselves (see [example](https://ospo.ucsc.edu/author/stephanie-lieggi/)): 
- Option A: email OSRE [administrators](mailto:slieggi@ucsc.edu) (currently: Stephanie Lieggi, Carlos Maltzahn)
  - Include name, title, affiliations, email, short bio, whether you are UC or Summer of Reproducibility mentor (or both), and, optionally, photo, web page and social media links.
- Option B (via git): 
  - Fork [git repository](https://github.com/carlosmalt/ucsc-ospo) (or combine with pull request of adding/updating a project above)
  - Create `/content/authors/USER` directory.
  - In that directory copy an `_index.md` file from another user and update it (see [example](https://raw.githubusercontent.com/carlosmalt/ucsc-ospo/main/content/authors/slieggi/_index.md))
    - Many icons are available (see [documentation](https://wowchemy.com/docs/getting-started/page-builder/#icons))
    - **IMPORTANT**: Under `user_groups:` add either `- University of California Mentors` or `- Summer of Reproducibility Mentors` (or both).
    - The bio and any other information goes below the frontmatter.

## Website framework

This website is based on [Wowchemy](https://wowchemy.com), a website framework using [Hugo](https://github.com/gohugoio/hugo) that can be deployed with GitHub and Netlify. The theme of the OSPO website is the [Research Group Theme](https://research-group.netlify.app/).
