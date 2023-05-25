---
title: "Verify the reproducibility of an experiment"
subtitle: "Capturing provenance from DS/ML workflows" 
authors: [jesselima]
tags: ["osre23", "uc", "data science", "machinelearning", "provenance", "reproducibility"]
date: 2023-05-24
lastmod: 2023-05-24
featured: false
draft: false

---

As part of the [noWorkflow](https://github.com/gems-uff/noworkflow) my [proposal](https://docs.google.com/document/d/1YMtPjZXcgt5eplyxIgQE8IBpQIiRlB9eqVSQiIPhXNU/edit?usp=sharing) under the mentorship of [João Felipe Pimentel](mailto:joao.pimentel@nau.edu) and [Juliana Freire](juliana.freire@nyu.edu) aims to implementing the necessary features to compare the provenance from two (or more) trials (i.e., execution of an experiment) and checking their reproducibility. This experiment consists in a tipical Data Science/Machine Learning experiment with all challenges they poses into common projects. 


### The tool

[noWorkflow](https://github.com/gems-uff/noworkflow) The noWorkflow project aims at allowing scientists to benefit from provenance data analysis even when they don’t use a workflow system. Also, the goal is to allow them to avoid using naming conventions to store files originated in previous executions. Currently, when this is not done, the result and intermediate files are overwritten by every new execution of the pipeline.


### The project

Although much can be said about what reproducibility means, the ability to replicate results in day-to-day Data Science and Machine Learning experiments can pose a significant challenge for individuals, companies, and uniersities. This challenge becomes even more pronounced with the emergence of analytics and IA, where scientific methodologies are extensively applied on an industrial scale beyond the limits of academia. Reproducibility now assumes a key role in productivity and accountability expected from Data Scientists, Machine Learning Engineers, and other roles engaged in ML/AI projects.

In the day-to-day, the pitfalls of non-reproducibility appear at different points of the experiment lifecycle. These challenges arise when multiple experiments need to be managed for an individual scientist or across a team of scientists. In a typical experiment workflow, reproducibility appears in the needs of dataset's provenance, needs in managing changes on hypothesis tests, going through managing system hardware and OS, and dealing with outputs of model instances. In academic environments, these issues can result in mistakes and inaccuracies. In companies, they can lead to inefficiencies and technical debts that are difficult to address in the future.


### Project Goals 
Implement an algorithm to compare the provenance from two (or more) trials (i.e., executions of an experiment) to check their reproducibility. The provenance stored in the relational (sqlite) database by noWorkflow 2 contains intermediate variable values from a trial. These values could be compared to check how much or where executions deviate from each other.

Specific tasks:

- Compare trials of the same script (Medium)
- Estimate how much on trial deviate from another (Medium)
- Consider different scripts and execution flows (Large)
- Indicate which parts of the scripts are not reproducible (Large)

### Project summary
- **Topics:** `Reproducibility`
- **Skills:** Python, SQL or SQLAlchemy ORM
- **Difficulty:** Moderate
- **Size:** Medium or large (175 or 350 hours)
- **Mentors:** [João Felipe Pimentel](mailto:joao.pimentel@nau.edu), [Juliana Freire](juliana.freire@nyu.edu)
