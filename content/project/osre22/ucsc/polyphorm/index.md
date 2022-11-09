---
title: "Polyphorm / PolyPhy"
authors: ["Oskar Elek"]
author_notes: ["OSPO Incubator Fellow, UC Santa Cruz"]
tags: ["osre22", "uc", "data science", "website design"]
date: 2022-11-07T10:15:56-07:00
lastmod: 2022-11-07T10:15:56-07:00
---

[Polyphorm](https://github.com/CreativeCodingLab/Polyphorm) is an agent-based system for reconstructing and visualizing *optimal transport networks* defined over sparse data. Rooted in astronomy and inspired by nature, we have used Polyphorm to reconstruct the [Cosmic web](https://youtu.be/5ILwq5OFuwY) structure, but also to discover network-like patterns in natural language data. You can find more details about our research [here](https://elek.pub/projects/Rhizome-Cosmology). Under the hood, Polyphorm uses a richer 3D scalar field representation of the reconstructed network, instead of a discrete representation like a graph or a mesh.

**PolyPhy** will be a Python-based redesigned version of Polyphorm, currently in the beginning of its development cycle. PolyPhy will be a multi-platform toolkit meant for a wide audience across different disciplines: astronomers, neuroscientists, data scientists and even artists and designers. All of the offered projects focus on PolyPhy, with a variety of topics including design, coding, and even research. Ultimately, PolyPhy will become a tool for discovering connections between different disciplines by creating quantitatively comparable structural analytics.

### Develop website for PolyPhy

- **Topics:** `Web Development` `Dynamic Updates` `UX`
- **Skills:** web development experience, good communicator, (HTML/CSS), (Javascript)
- **Difficulty:** Moderate
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu)

Develop a clean and welcoming website for the project. The organization needs to reflect the needs of PolyPhy users, but also provide a convenient entry point for interested project contributors. No excessive pop-ups or webjunk.

Specific tasks:
- Work with mentors on understanding the context of the project.
- Port the contents of the [repository page](https://github.com/CreativeCodingLab/Polyphorm) to a dedicated website.
- Design the structure of the website according to best OS practices.
- Work with the visual designer (see below) in creating a coherent and organic presentation.
- Interactively link important metrics from the project dev environment as well as documentation.

### Design visual experience for PolyPhy's website and presentations

- **Topics:** `Design` `Art` `UX`
- **Skills:** vector and bitmap drawing, sense for spatial symmetry and framing, (interactive content creation), (animation)
- **Difficulty:** Moderate
- **Size:** Medium (175 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu)

Develop visual content for the project using its main themes: nature-inspired computation, biomimetics, interconnected structures. Aid in designing visual structure of the website as well as other public-facing artifacts.

Specific tasks:
- Work with mentors on understanding the context of the project.
- Design imagery and other graphical elements to visually (re-)present PolyPhy.
- Work with the technical writer (see below) in designing a coherent story.
- Work with the web developer (see above) in creating a coherent and organic presentation.

### Write PolyPhy's technical story and content

- **Topics:** `Writing` `Documentation` `Storytelling`
- **Skills:** experienced writing structured text over 10 pages, well read, (technical or scientific education)
- **Difficulty:** Moderate
- **Size:** Medium or Large (175 or 350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu)

Integral to PolyPhy's presentation is a story that the users and the project contributors can relate to. The objective is to develop the verbal part of that story, as well as major portions of technical documentation that matches it. The difficulty of the project is scalable.

Specific tasks:
- Work with mentors on understanding the context of the project.
- Write different pages of the project website.
- Work with mentors to improve project's written community practices (diversity, communication).
- Write and edit narrative and explanatory parts of PolyPhy's documentation.
- Work with the visual designer (see above) in designing a coherent story.

### Video tutorials and presentation for PolyPhy

- **Topics:** `Video Presentation` `Tutorials` `Didactics`
- **Skills:** video editing, creating educational content, communication, (native or fluent in another language)
- **Difficulty:** Easy-Moderate
- **Size:** Medium or Large (175 or 350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu), [Drew Ehrlich](mailto:deehrlic@ucsc.edu)

Create a public face for PolyPhy that reflects its history, context, and teaches its functionality to users in different degrees of familiarity.

Specific tasks:
- Work with mentors on understanding the context and history of the project.
- Interview diverse project contributors.
- Create a video documenting PolyPhy's history, with roots in astronomy, complex systems, fractals.
- Create a set of tutorial videos for starting and intermediate PolyPhy users.
- Create an accessible template for future tutorials.

### Implement heterogeneous data I/O ops

- **Topics:** `I/O Operations` `File Conversion` `Numerics` `Testing`
- **Skills:** Python, experience working with scientific or statistical data, good debugging skills
- **Difficulty:** Moderate-Challenging
- **Size:** Medium or Large (175 or 350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu), [Anisha Goel](mailto:anishagoel14@gmail.com)

By default, PolyPhy operates with an unordered set of points as an input and scalar fields (float ndarrays) as an output, but others are applicable as well. Design and implement interfaces to load and export different data formats (CSV, OBJ, HDF5, FITS...) and modalities (points, meshes, density fields). The difficulty of the project can be scaled based on contributor's interest.

Specific tasks:
- Research which modalities are used by members of the target communities.
- Implement modular loaders for the inputs and an interface to PolyPhy core.
- Implement exporters for simulation datasets and visualization captures.
- Write testing code for the above.
- Integrate external packages as necessary.

### Setup CI/CD for PolyPhy

- **Topics:** `Continuous Integration` `Continuous Deployment` `DevOps`
- **Skills:** experience with CI/CD, GitHub, Python package deployment
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu), [Anisha Goel](mailto:anishagoel14@gmail.com)

The objective is to setup a CI/CD pipeline that automates the build testing and deployment of the software. The resulting process needs to be robust to contributor errors and work in the distributed conditions of a diverse contributor base.

Specific tasks:
- Automate continuous building, testing, merging and deployment for PolyPhy in GitHub.
- Publish the CI/CD metrics and build assets to the project webpage.
- Work with other contributors in educating them about the best practices of using the developed CI/CD pipeline.
- Add support for automated packaging using common management systems (pip, Anaconda).

### Refine PolyPhy's UI and develop new functional elements

- **Topics:** `UI/UX` `Visual Experience`
- **Skills:** Python programming, UI/UX development experience, (knowledge of graphics)
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu), [David Abramov](mailto:dabramov@ucsc.edu)

The key feature of PolyPhy is its interactivity. By interacting with the underlying simulation model, the user can adjust its parameters in real time and respond to its behavior. For instance, an astrophysics expert can load a dataset of 100k galaxies and reconstruct the large-scale structure of the intergalactic medium. A responsive UI combined with real-time visualization allows them to judge the fidelity of the reconstruction and make necessary changes.

Specific tasks:
- Implement a platform-agnostic UI to house PolyPhy's main rendering context as well as secondary analytics.
- Work with the visualization developer (see below) to integrate the rendering functionality.
- Optimize to UI's performance.
- Test the implementation on different OS platforms.

### Create new data visualization regimes

- **Topics:** `Interactive Visualization` `Data Analytics` `3D Rendering`
- **Skills:** basic graphics theory and math, Python, GPU programming, (previous experience visualizing novel datasets)
- **Difficulty:** Challenging
- **Size:** Large (350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu), [David Abramov](mailto:dabramov@ucsc.edu)

Data visualization is one of the core components of PolyPhy, as it provides a real-time overview of the underlying MCPM simulation. Through the feedback provided by the visualization, PolyPhy users can adjust the simulation model and make new findings about the dataset. Various operations over the reconstructed data (e.g. spatial searching) as well as important statistical summaries also benefit from clear visual presentation.

Specific tasks:
- Develop novel ways of visualizing scientific data in PolyPhy.
- Work with diverse data modalities - point clouds, graphs, scalar and vector fields.
- Add support for visualizing metadata, such as annotations and labels.
- Create UI elements for plotting statistical summaries computed in real-time.

### Discrete graph extraction from simulated scalar fields

- **Topics:** `Graph Theory` `Data Science`
- **Skills:** good understanding of discrete math and graph theory, Python, (GPU programming)
- **Difficulty:** Challenging
- **Size:** Large (350 hours)
- **Mentors:** [Oskar Elek](mailto:oelek@ucsc.edu), [Farhanul Hasan](mailto:farhasan@nmsu.edu)

Develop a custom method for graph extraction from scalar field data produced by PolyPhy. Because PolyPhy typically produces network-like structures, representing these structures as weighted discrete graphs is very useful for efficiently navigating the data. The most important property of this abstracted representation is that it preserves the topology of the base scalar field by navigating the 1D ridges of the scalar field.

Specific tasks:
- Become familiar with different algorithms for graph growing and skeleton extraction.
- Implement the most suitable method in PolyPhy, interpreting the source scalar field as a throughput (transport) network. The weights of the resulting graph need to reflect the source throughputs between the respective node locations.
- Implement common graph operations, e.g. hierarchical clustering and reduction, shortest path between two nodes, range queries.
- Optimize the runtime of the implemented methods.
- Work with the visualization developer (see above) to visualize the resulting graphs.
