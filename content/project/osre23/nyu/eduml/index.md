---
title: "Using Reproducibility in Machine Learning Education"
summary: 'The computer science and engineering classroom is as essential part of the reproducibility "ecosystem" - because of broad reach and potential for big impact, and because for many students, the classroom is their first exposure to research in their field.'
authors: [ffund]
author_notes: ["Research Assistant Professor, Department of Electrical and Computer Engineering, New York University"]
tags: ["osre23", "reproducibility"]
date: 2023-01-18T00:00:00Z
lastmod: 2023-01-18T00:00:00Z
---

Lead Mentor: [Fraida Fund](mailto:ffund@nyu.edu)  

The computer science and engineering classroom is as essential part of the reproducibility "ecosystem" - because of broad reach and potential for big impact, and because for many students, the classroom is their first exposure to research in their field. For machine learning in particular, reproducibility is an important element of the research culture, and can be a valuable part of any introductory or advanced courses in the field. These projects will develop highly interactive open educational resources, that may be adopted by instructors of graduate or undergraduate machine learning courses to incorporate more instruction about reproducibility and reproducible research.

### Introducing "levels" of reproduction and replication in ML

* **Topics**: Machine learning, reproducibility, education
* **Skills**: Python, machine learning, writing
* **Difficulty**: Medium
* **Size**: 350 hours
* **Mentor(s)**: {{% mention ffund %}} and TBD
* **Contributor(s)**: {{% mention MSaeed %}}

In machine learning, replicating a published result to confirm the validity of the experimental results and the broader conclusions of the paper can take several forms, with increasing levels of effort:

* using authors' code and pre-trained weights, run the model on the same benchmarks as the original paper
* training a model using authors' code and published hyperparameters,
* training a model using authors' code and a new hyperparamter search,
* validating the authors' code e.g. with unit tests, in addition to training,
* re-implementing the model,
* designing additional experiments to validate that the suggested mechanism is in fact responsible for the result,
* and more.

This project will develop interactive materials (using one or more exemplar published results) to illustrate and to highlight relevant aspects and pitfalls of each of these "levels" of reproduction and replication.

### Packaging existing reproducible results for the ML classroom

* **Topics**: Machine learning, reproducibility, education
* **Skills**: Python, machine learning, writing
* **Difficulty**: Medium
* **Size**: 350 hours
* **Mentor(s)**: {{% mention ffund %}} and TBD
* **Contribuor(s)**: {{% mention indianspeedster}}, {{% mention kokoedwin %}}

The goal is to make it easier for instructors to expose students to state-of-the-art research in the classroom. This project will work with an existing set of recent reproducible results in machine learning, and will package them for easier consumption by students and more effective use in the classroom. This may include, but is not necessarily limited to:

* Re-validating the result and re-packaging along with computational environment on an open access testbed
* Creating tutorial material around the result, including interactive visualizations to demonstrate key elements of the work
* Creating one-click demos for applying the model/technique to a new test sample
* Curating test samples to highlight important advantages and limitations of the result
* Creating assessment questions and sample "solutions" that instructors may use to "assign" the work to students

