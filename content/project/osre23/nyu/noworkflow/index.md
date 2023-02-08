---
title: "noWorkflow"
authors: [jpimentel, julianafreire]
author_notes: ["Northern Arizona University", "New York University"]
tags: ["osre23", "reproducibility", "provenance"]
date: 2023-02-07
lastmod: 2023-02-07
---

The [noWorkflow](https://github.com/gems-uff/noworkflow) project aims at allowing scientists to benefit from provenance data analysis even when they don't use a workflow system. Also, the goal is to allow them to avoid using naming conventions to store files originated in previous executions. Currently, when this is not done, the result and intermediate files are overwritten by every new execution of the pipeline.

noWorkflow was developed in Python, and it is currently able to capture provenance of Python scripts using Software Engineering techniques such as abstract syntax tree (AST) analysis, reflection, and profiling, to collect provenance without the need of a version control system or any other environment.

At the moment of this writing, the main version of noWorkflow is in the 2.0-alpha branch. We intend to release it before the summer.

### Verify the reproducibility of an experiment

- **Topics:** Reproducibility
- **Skills:** Python, SQL or SQLAlchemy ORM
- **Difficulty:** Moderate
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** {{% mention jpimentel %}}, {{% mention julianafreire %}}

Implement an algorithm to compare the provenance from two (or more) trials (i.e., executions of an experiment) to check their reproducibility. The provenance stored in the relational (sqlite) database by noWorkflow 2 contains intermediate variable values from a trial. These values could be compared to check how much or where executions deviate from each other.

Specific tasks:
- Compare trials of the same script (Medium)
- Estimate how much on trial deviate from another (Medium)
- Consider different scripts and execution flows (Large)
- Indicate which parts of the scripts are not reproducible (Large)
  
### Control levels of provenance collection

- **Topics:** Log experiments
- **Skills:** Python
- **Difficulty:** Challenging
- **Size:** Large (350 hours)
- **Mentors:** {{% mention jpimentel %}}, {{% mention julianafreire %}}

Add support for different levels of provenance collection in noWorkflow 2. Currently, noWorkflow 2 collects Python construct evaluations and all the dependencies among the evaluations. However, this collection is inefficient, since some of the collected provenance may not be necessary for end-users. In this project, it is desirable to provide ways to temporarily disable the provenance collection  and to manually indicate the provenance in this situation.

Specific tasks:
- Disable the collection inside specific functions (through decorators?)
- Disable the collection inside specific regions of the code (through with statements?)
- Collect only function activations in a region, instead of all variable dependencies
- Disable the collection of specific modules
- Design a DSL to express general dependencies for parts of the code where the collection is disabled

### Upgrade noWorkflow collection to support new Python constructs

- **Topics:** Log experiments
- **Skills:** Python
- **Difficulty:** Moderate
- **Size:** Large (350 hours)
- **Mentors:** {{% mention jpimentel %}}, {{% mention julianafreire %}}

Implement new AST transformations for provenance collection. While noWorkflow 2 works for newer Python versions, most of its implementation was targeted at Python 3.7. Newer Python versions have new constructs in which the provenance is ignored.

Specific tasks:
- Identify which AST constructs implementations are missing
- Design AST transformations to execute functions before and after the evaluation of the constructs
- Create the dependencies for the new constructs