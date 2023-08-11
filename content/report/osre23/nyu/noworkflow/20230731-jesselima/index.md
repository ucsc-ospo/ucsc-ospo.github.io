---
title: "[Mid-term] Capturing provenance into Data Science/Machine Learning workflows"
subtitle: "blog post for noworkflow project" 
authors: [jesselima]
tags: ["osre23", "nyu", "data science", "machine learning", "provenance", "reproducibility"]
date: 2023-07-31
lastmod: 2023-07-31
draft: false
featured: false
image:
caption: ""
focal_point: "Smart"
preview_only: false
---

This post describes our midterm work status and some achievements we have done so far in [the project](https://docs.google.com/document/d/1YMtPjZXcgt5eplyxIgQE8IBpQIiRlB9eqVSQiIPhXNU/edit#heading=h.nnxl1g16trg0) for the [noWorkflow](https://ucsc-ospo.github.io/project/osre23/nyu/noworkflow/) package. 


#### The initial weeks

I started doing a bibliographical review on reproducibility in the Data Science (DS) and Machine Learning (ML) realms. It was a new subject to me, and I aimed to build a more robust theoretical background in the field. Meanwhile, I took notes in [this series of posts](https://jaglima.github.io/). 

Then, as planned, I integrated with the current noWorkflow supporters in order get a broader view of the project and their contributions. Additionally, [Juliana Freire](https://ucsc-ospo.github.io/author/juliana-freire/), [Joao Felipe Pimental](https://ucsc-ospo.github.io/author/joao-felipe-pimentel/) and I set up a weekly one-hour schedule to keep track of my activities. 

### Brainstormed opportunities

At the beginning of June, we also met with other project supporters to brainstorm about our initial proposal. From this meeting, we came up with a plan on how technically approach a noWorkflow new feature in Data Science and Machine Learning experimental management.

In this brainstorm, we aligned that _Jupyter Notebooks are, by far, the most frequent set up in DS/ML computational experiments. They established themselves as the fundamental artifact by embedding code, text and enabling execution and visualization. Entire experiments are created and kept in Jupyter notebooks until they are sent to production. And the opportunity at hand is to integrate noWorkflow with Jupyter Notebooks_. 
Then, our mid-term goal was adapted from the original plan of only selecting and executing a prototypical ML experiment. We added the goal of paving the way for providing a tagging feature for Notebook cells. 

More specifically, DS/ML experimental workflows usually have well-defined stages composed of _data reading_, _feature engineering_, _model scoring_, and _metrics evaluation_.  In our  dream space, the user would tag a cell in their experiment, enabling the capture of the tagged metadata into a database. This step integrates the ultimate goal of facilitating comparisons, management, and even causal inference across different trials of a DS/ML experiment. 

### Current deliverables

So, based on our plans, we create a separate table to store the metadata from cell tagging. This table stores the cell hash codes and information to match the code executed within a cell. As a result, we can store tags and the activation ids of the cells enabling us to identify a cell containing a given stage in a DS/ML experiment. 

The second feature implemented was tagging a specific variable. In the same way for a cell, now it is possible to stamp a given variable with a tag, keeping its name, id, and received value in this separated table.

Finally, we worked on displaying the dependencies of a given variable. In this case, by tagging a given variable, we can display the other variables, values, and cells activated in its construction. Then, we can visualize the dependencies that contributed to its final value.

For an overview of current developments, please refer to my [fork of the main project](https://github.com/jaglima/noworkflow/tree/stage_tagging).

### Challenges

During this period, we had to make choices along the way. For instance, capturing the provenance of cells through tags is a different solution than tagging code chunks in scripts. In this case, we decided to stick with tagging Notebook cells at this moment. We also opted to start storing the metadata to enable comparisons between trials rather than focus on a sophisticated graphic and user-friendly cell tagging system. We also opted to keep this metadata info stored in a separate table in the database.


### Next steps

In the second half of the summer, our goal is to integrate these features in order to proceed with comparisons among experiments. Such comparisons would use the tagged variables as the hyperparameters of DS/ML experiments or key variables to assess the experiments, such as errors or scores. As a result, we will be able to compare the results of two trials in a more accurate, and easily reproducible experiment.

