---
title: "Mid-term blog post for noworkflow"
subtitle: "Capturing provenance into Data Science/Machine Learning workflows" 
authors: [jesselima]
tags: ["osre23", "ucsc", "nyu", "data science", "machinelearning", "provenance", "reproducibility"]
date: 2023-05-24
lastmod: 2023-05-24
draft: false
featured: false

# Featured image

# To use, add an image named `featured.jpg/png` to your page's folder.

# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.

image:
caption: ""
focal_point: "Smart"
preview_only: false
---

This post describes our midterm work status and some achievements we have done so far in the project [proposal](https://docs.google.com/document/d/1YMtPjZXcgt5eplyxIgQE8IBpQIiRlB9eqVSQiIPhXNU/edit#heading=h.nnxl1g16trg0) for the [noWorkflow](https://ucsc-ospo.github.io/project/osre23/nyu/noworkflow/) package. 


#### The initial weeks

I started doing a bibliographical review on reproducibility in the Data Science (DS) and Machine Learning (ML) realms. It was a new subject to me, and I aimed to build a more robust theoretical background in the field. Meanwhile, I took notes in [this series of posts](https://jaglima.github.io/). 

Then, as planned, I integrated with the current noWorkflow supporters in order get a broader view about the project and their contributions. Adittionally, [Juliana Freire](https://ucsc-ospo.github.io/author/juliana-freire/), [Joao Felipe Pimental](https://ucsc-ospo.github.io/author/joao-felipe-pimentel/) and I set up a weekly one-hour schedule to keep track of my activities. 

### Brainstorming opportunities

At the beginnig of June we also met with other project supporters to brainstorm about our initial proposal. From this meeting, we came up with a plan on how technically approach a noWorkflow new feature in the Data Science and Machine Learning experimental management. 

In this brainstorm, we reinforced that Jupyter Notebooks are, by far, the most frequent setup in DS/ML computational experiments. They established themselves as the fundamental artifact by embedding code, text and enabling execution and visualization. Entire experiments are created and kept in Jupyter notebooks until they are sent to production. And the opportunity at hand is to integrate noWorkflow with Jupyter Notebooks. 

Then, our mid-term goal was adapted from the original plan of only selecting and executing a prototypical ML experiment. We added the goal of paving the way for providing a tagging feature for Notebook cells. Specifically, DS/ML experimental typical workflows have well-defined stages, usually composed of _data reading_, _feature engineering_, _model scoring_, and _metrics evaluation_.  In our  dreamspace, an user would tag a cell in their experiment, enabling the capture of the tagged metadata into a database. This step integrates the ultimate goal of facilitating comparisons, management, and even causal inference across different trials of a DS/ML experiment. 

### Getting busy

So, based on our plans, I first turned to create a separate table to store the metadata from cell tagging. This table should store the cell hash codes and information that can be matched with the code executed within a cell. As a result, in this initial phase, we have a separate *table storing tags and the activation ids of the cells, enabling identify them as part of a given stage in the DS/ML experiment*. 

Simultaneously, I had to encapsulate the cell marking code into a function to make it cleaner. All this was done in Python programming, using fundamentals of OO development and using Git as the tool for versioning.

During this period, we also had to make choices along the way. For instance, capturing the provenance of cells through tags is a different solution than tagging code chunks in scripts. In this case, we decided to stick with tagging Notebook cells at this moment. We also opted to start storing the metadata to enable comparisons between trials rather than focus on a sophisticated graphic and user-friendly cell tagging system. We also opted to keep this metadata info stored in a separate table in the database.

### Next steps

In the second half of the summer, our goal is to integrate this current table with the activation metadata from the execution and then match the tags with the operations they enclose to proceed with comparisons among experiments. 

Also, we want to be able to mark some variables to be tracked. These variables can be hyperparameters of DS/ML experiments or key variables to assess the experiments, as errors or scores. As a result, we will be able to track code and parameters, their stage in the experiment and provide more efficient, accurate, and reproducible experiments.

For an overview of current developments in this project, anyone can acesse this [fork of the original project](https://github.com/jaglima/noworkflow).


