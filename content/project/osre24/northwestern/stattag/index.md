---
title: "StatTag: Connecting statistical software to Microsoft Word"
authors: [lrasmus]
author_notes: ["Northwestern University"]
tags: [osre24, reproducibility, csharp]
date: 2024-01-22
lastmod: 2024-01-22
---

StatTag is a free, [open-source](https://github.com/stattag) software plug-in for conducting reproducible research. It facilitates the creation of dynamic documents using Microsoft Word documents and statistical software, such as Stata, SAS, R, and Python. Users can use StatTag to embed statistical output (estimates, tables and figures) into a Word document and then with one click individually or collectively update output with a call to the statistical program.

What makes StatTag different from other tools for creating dynamic documents is that it allows for statistical code to be edited directly from Microsoft Word.  Using StatTag means that modifications to a dataset or analysis no longer require transcribing or re-copying results into a manuscript or table.

StatTag works by interpreting specially formatted comments ("tags") within a code file.  StatTag then reads the code file, executes the code through the corresponding language interpreter, formats the results, and inserts them into the Word document as a field.

There are versions of StatTag for both Microsoft Windows and macOS. Proposed projects here are specific to the Microsoft Windows version, which is developed in the C# programming language.

**Additional Information:**

* [StatTag homepage](https://sites.northwestern.edu/stattag/)
* [StatTag on GitHub](https://github.com/stattag)
* [Welty et al., "Facilitating reproducible research through direct connection of data analysis with manuscript preparation: StatTag for connecting statistical software to Microsoft Word"](https://pubmed.ncbi.nlm.nih.gov/33215069/)


### Support Additional Programming Languages

* Topics: `reproducibility`, `statistics`
* Skills: C# and one of: MATLAB, Octave, SQL, Julia
* Difficulty: Medium
* Size: Medium or large (175 or 350 hours)
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

