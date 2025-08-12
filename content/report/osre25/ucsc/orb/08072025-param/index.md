---
title: "Midterm Report: Learning and Building ORB"
subtitle: ""
summary: "A midpoint update on the ORB project"
authors: 
  - param
tags: ["osre25", "uc", "orb"]
categories: ["open source", "web development"]
date: 2025-08-07
lastmod: 2025-08-07
featured: true
draft: false

---

## Project Overview

UC ORB is an open-source platform developed to increase visibility and engagement with open source projects across the University of California system.

By providing a structured and searchable repository browser, ORB makes it easier for researchers, students, and collaborators to discover relevant open source initiatives, track their impact, and connect with contributors. It also helps campuses demonstrate the value of their open source output to potential funders and institutional partners.


## Progress So Far

Significant progress has been made in building out core features of the ORB Showcase platform:

### Searching and Filtering Options
Users can now search and filter repositories using multiple criteria:

- Development Team / UC Campus
- Programming Language
- License Type
- Topic / Domain Area

These filtering tools make it easy to explore the growing set of repositories in a meaningful and personalized way.

Pagination has been added to ensure scalability and smooth performance, even as the number of projects continues to grow.

### Repository Details View
Each repository page now displays rich metadata and contextual information, including:

README preview – offering a quick look at the project’s purpose and usage

License – clearly indicating how the project can be used or adapted

Contributors and Funders – acknowledging the people and institutions behind the work


## What's Next

As we prepare UC ORB for public launch, we’re focused on improving the backend workflow and addressing some key challenges:

⚙️ GitHub Workflow Challenges
Creating a GitHub-first workflow for adding repositories is powerful, but also tricky:

GitHub Actions cannot be triggered by API calls from a backend directly, which limits automation via server-side tools.

The GitHub bot has permission limitations, especially when it comes to interacting with PRs and validating submissions outside of standard GitHub UI flows.

I’m currently working on designing a more robust and maintainable workflow to handle these edge cases, including:

A standalone script that can add repositories directly to the database, bypassing the need for a pull request and enabling more flexible internal submissions.

Better logging and validation to ensure consistency between the file-based data model and the live PostgreSQL database.


# Reflection

This project has been a great learning experience despite challenges with Frontend, Backend, GitHub Actions / Bots and APIs, it’s been exciting to build a platform that highlights open source work across the UC system.

I'm looking forward to what's coming next as we get closer to launching ORB.