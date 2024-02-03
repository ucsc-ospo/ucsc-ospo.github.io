---
title: "SLICES/pos: Reproducible Experiment Workflows"
authors: [gallenmu, carle]
author_notes: ["Technical University of Munich"]
tags: [osre24, reproducibility, python, SLICES-RI]
date: 2024-02-06
lastmod: 2024-02-06
---

[SLICES-RI](https://www.slices-ri.eu/) is a european research initiative aiming to create a digital research infrastructure providing an experimental platform for the upcoming decades.
One of the main goals of this initiative is the creation of fully reproducible experiments.
The SLICES research infrastructure will consist of different experiment sites focusing of different research domains such as AI experiments, Cloud and HPC-driven experiments, or investigations on wireless networks.

To achieve reproducibility, the research group on network architectures and services of the Technical University of Munich develops the [SLICES plain orchestrating service (SLICES/pos)](https://dl.acm.org/doi/10.1145/3485983.3494841).
This framework supports a fully automated structured experiment workflow.
The structure of this workflow act as a template for the design of experiment.
Users that adhere to this template will create inherently reproducible experiments, a feature we call reproducible-by-design.

The SLICES/pos framework currently exists in two versions:
A fully-managed pos deployment, that uses the SLICES/pos framework to manage the entire testbed and a hosted pos deployment.
The hosted SLICES/pos deployment is a temporary deployment that runs inside existing testbeds such as [Chameleon](https://chameleoncloud.org/) or [CloudLab](https://cloudlab.us/).
The host

**Additional Information:**

* [StatTag homepage](https://sites.northwestern.edu/stattag/)
* [StatTag on GitHub](https://github.com/stattag)
* [Welty et al., "Facilitating reproducible research through direct connection of data analysis with manuscript preparation: StatTag for connecting statistical software to Microsoft Word"](https://pubmed.ncbi.nlm.nih.gov/33215069/)


### Support Additional Programming Languages

* Topics: `reproducibility`, `statistics`
* Skills: Python
* Difficulty: Medium
* Size: Large (350 hours)
* Mentor: {{% mention lrasmus %}}

Following the same structure used for other language support in StatTag, develop support for a new programming language (suggested languages are provided, but applicants can propose others).  This will include:

* Creating a Parser class to support StatTag-specific interpretation of results (e.g., identifying a line of code that is writing to a CSV file, then loading that CSV file)
* Creating an Automation class that manages communication with the supported programming language's interpreter.  Python support uses a Jupyter kernel, and both SAS and Stata support invoke DLLs directly.
* Integrating the language into the UI (e.g., allowing it to be a valid code file, adding the icon for the code file to the UI)
* Additional setup/configuration as needed (e.g., SQL support would require secure configuration for connecting to the databse server).

Develop unit tests to demonstrate code is functioning.  Create test scripts in the implemented language to exercise and demonstrate end-to-end execution.


### Process Tags in Jupyter Notebooks

* Topics: `reproducibility`, `jupyter`
* Skills: C#, Jupyter Notebooks, Python
* Difficulty: Medium
* Size: Medium (175 hours)
* Mentor: {{% mention lrasmus %}}

StatTag uses

StatTag currently has support for Python, and utilizes the Jupyter kernel to interact with Python.  However, we currently do not fully support processing StatTag 'tags' in a Jupyter notebook.

Following the same structure used for RMarkdown integration in StatTag, develop support for Jupyter Notebooks in StatTag.  StatTag should be able to:

* Take as input one or more Jupyter Notebooks
* Confirm that the Jupyter Notebook uses Python
* Identify StatTag formatted tags within the notebook
* Pass relevant code to the Python processor already implemented in StatTag

In addition, develop unit tests to demonstrate code is functioning as intended.  Create test Jupyter Notebooks to exercise and demonstrate end-to-end execution.

