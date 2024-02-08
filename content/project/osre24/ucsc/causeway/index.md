---
title: "Causeway: Learning Web Development Through Micro-Roles"
authors: [dlee105]
author_notes: ["Assistant Professor, UC Santa Cruz"]
tags: ["osre24", "uc", "web development", "educational technologies"]
date: 2024-02-07
lastmod: 2024-02-07
---

[Causeway](https://tech4good-causeway.web.app/#/tutorial/quarter-goals?c=01-quarter-goals-component&r=01-component-elements&s=01-intro-to-causeway) is a platform for learning to develop web applications using an Angular, RxJS, NgRx, and Firebase stack. Most online coding tutorials focus on covering the technical syntax or features of a language or framework, which means that new developers don’t have great resources for building a holistic picture of how everything they learn connects to actually developing a complex web application. Causeway breaks down the process of developing a web application into a hierarchy of micro-roles which provides learners with a clear pathway for learning that also translates to a clear process for developing an application. In the longer future, this would also enable learners to easily contribute to projects as they learn through taking on micro-roles for yet-to-be-developed projects. The platform uses the [Stackblitz WebContainer API](https://developer.stackblitz.com/platform/api/webcontainer-api) to run full applications in the browser for interactive learning. 

Thus far, we have developed a version of the platform that walks learners through the process of developing presentational components of a web application as well as smart components / containers that contain multiple presentational components and are responsible for fetching data from the backend and handling events and updates to the database. This content is still using Angular 13 and needs to be updated to Angular 17, as well as to make some improvements in our use of RxJS, NgRx, and Firebase. We’d also like to extend the content in multiple ways including: 1) extending the walkthrough to more components and containers besides the single example we have, ideally in a way that covers a complete application, and 2) extending beyond components and containers to cover defining database entities and relationships. We’d also like to develop a learning dashboard where users can see the different micro-roles and lessons that they’ve completed or that are upcoming for the project they are working on.


### Causeway / Improving the Core Infrastructure and Experience

The proposed work includes updating the platform and the example infrastructure within the platform to the latest version of Angular and other associated libraries, implementing and testing logging and analytics, implementing a learning dashboard for users, and time permitting, creating new modules to cover defining database entities and relationships. Both roles will also contribute to running usability studies and documenting the platform so that it can be open-sourced.

- **Topics:** Web Development, Educational Technologies, Angular
- **Skills:** Web development experience, HTML, CSS, Javascript, Angular, RxJS, NgRx, Firebase
- **Difficulty:** Medium to Hard
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "dlee105" %}}

### Causeway / Extend the Learning Scope and Experience 
The proposed work includes extending the component and container walkthroughs to cover a complete interactive application. This means writing a separate simple application, and organizing the code required to do so into units of work organized by our micro-role structure. Both roles will also contribute to running usability studies and documenting the platform so that it can be open-sourced.

- **Topics:** Web Development, Educational Technologies, Angular
- **Skills:** Web development experience, HTML, CSS, Javascript, Angular, RxJS, NgRx, Firebase
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** {{% mention "dlee105" %}}
