---
title: "Data leakage in applied ML: reproducing examples of irreproducibility" 
authors: [ffund]
author_notes: ["Research Assistant Professor, Department of Electrical and Computer Engineering, New York University"]
tags: [osre24, reproducibility, machine learning]
date: 2024-02-21
lastmod: 2024-02-21
---

- **Topics:** applied machine learning, data leakage, reproducibility
- **Skills:** Python, data analysis, machine learning
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** {{% mention ffund %}} and TBD

**Project Idea Description**

Data leakage [has been identified](https://www.cell.com/patterns/pdfExtended/S2666-3899(23)00159-9) as a major cause of irreproducibility of a paper's findings, when machine learning techniques are applied to problems in science. Data leakage includes errors such as:

* pre-processing before splitting into training/test sets
* feature selection before splitting into training/test sets
* duplicated data points in both training and test sets
* temporal leakage (e.g. shuffled K-fold cross validation with temporal data)
* group leakage (e.g. shuffled K-fold cross validation with data that has group structure)

and leads to an overly optimistic evaluation of model performance, such that the finding may no longer be the same when the error is corrected.

Despite the seriousness of this problem, data leakage is often not covered in introductory machine learning courses, and many users of machine learning across varied science domains are unaware of it. Even those who have learned "rules" for avoiding data leakage (e.g. "never do feature selection on the test set") may not understand the reasons for these "rules", and how important they are for ensuring that the final result is valid and reproducible.

The goal of this project is to create *learning materials* demonstrating how instances of data leakage invalidate a result. These materials should be easily adoptable by instructors teaching machine learning in a wide variety of contexts, including those teaching a non-CS audience. To achieve this, the project proposes to re-implement published results that have been affected by data leakage, and package these implementations along with supporting material in a format suitable for use in classrooms and by independent learners. For each "irreproducible result", the "package" should include - 

* a re-implementation of the original result
* an explanation of the data leakage problem affecting the result, with an implementation of a "toy example" on synthetic data
* a re-implementation of the result without the data analysis error, to show how the finding is affected
* and examples of exam or homework questions that an instructor adopting this package may use to assess understanding.


**Writing a successful proposal for this project**

A good proposal for this project should include, for at least a few "types" of data leakage mentioned above - 

* a specific published result that could be used as an exemplar (you may find ideas among the review papers listed [here](https://reproducible.cs.princeton.edu/#rep-failures))
* a brief description of the details of the experiment that will reproduce that result (e.g. what data is used, what machine learning technique is used, what are the hyperparameters used for training)
* and an explanation of why this result is suitable for this use (it uses a publicly available dataset, a machine learning technique that is familiar and accessible to students in an introductory course, the paper has sufficient detail to reproduce the result, etc.)

The contributor will need to create learning materials that are written in a clear, straightforward, and concise manner, without unncessary jargon. The proposal should show evidence of the contributor's writing abilities.

**Github link**

There is no pre-existing Git repository for this project - at the beginning of the summer, the contributor will create a new repository in the [Teaching on Testbeds](https://github.com/teaching-on-testbeds/) organization, and the project materials will "live" there.

To get a sense of the type of code you would be writing, here is an example of a learning module related to data leakage (however, it is not in the format described above): [Beauty in the Classroom](https://colab.research.google.com/github/ffund/ml-notebooks/blob/master/notebooks/4-linear-regression-case-study-part-2.ipynb)

**Project Deliverables**

- "Packages" of learning materials for teaching about common types of data leakage 
- [Trovi](https://chameleoncloud.org/experiment/share/) artifacts for "playing back" each of the "packages"





