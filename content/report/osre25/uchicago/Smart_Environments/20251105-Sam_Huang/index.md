---
title: "Final Report for Smart Environments"
authors: [Sam Huang, marshalp]
author_notes: ["University of Chicago", "University of Chicago"]
tags: ["osre25", "reproducibility", "machine learning", "OS"]
date: 2025-11-05
lastmod: 2025-11-05
---

## Introduction

The process of creating the necessary software environment for code to run is a significant challenge in software development. Given a piece of open-source software intended for research, setting up the environmental dependencies to run the software could take significant manual effort. Existing automation methods struggle due to the complexity of managing diverse languages, dependencies, and hardware. In Smart Environments, I have created ENVAGENT, a general multi-agent framework designed to automate the construction of executable environments for reproducing research prototypes from top-tier conferences and journals. While reproducibility has become a growing concern in the research community, the process of setting up environments remains time-consuming, error-prone, and often poorly documented.

To assess this capability, a new benchmark, ENVBENCH, was created, containing 54 popular projects across seven languages. Results show ENVAGENT dramatically improves environment construction compared to current agents (+16.2%). Furthermore, the system shows initial promise in dynamically adjusting cloud-based hardware resources based on the code’s needs.

![EnvGym Cover](cover.png)

## Method

### EnvAgent

The EnvAgent I created during my time at OSRE utilizes a multi-agent workflow to automatically build software execution environments. The process is structured into three phases: preparation, construction, and refinement.

Phase 1 (Preparation): Specialized agents collect information about the software repository – its structure, relevant files, and the host system’s hardware specifications (CPU, memory, etc.). This data is then used by a planning agent to generate a detailed, step-by-step instruction set for creating a functional Dockerfile.

Phase 2 (Construction): Two agents work in tandem: one generates or modifies the Dockerfile based on the plan, while the other executes the Dockerfile within an isolated container, capturing any errors.

Phase 3 (Refinement): A final agent analyzes the container execution data, identifying areas for improvement in the Dockerfile. This process repeats until a stable, executable environment is achieved.

To improve efficiency, EnvAgent incorporates rule-based tools for predictable tasks like directory setup and log management, reducing the need for complex agent reasoning. This combination of intelligent agents and automated routines ("scaffolding") ensures a robust and adaptive system.

### EnvEval Benchmark

In addition to the agent, one significant contribution is the manual curation of a benchmark that measures the quality of generated environments. EnvEval is a benchmark specifically designed to assess environment setup qualities across 54 carefully curated open-source repositories. They are chosen from both Chameleon reproducible artifacts and Multi-SWE-bench dataset. EnvEval contains json rubrics that can be used to automatically determine the quality of constructed environments.

Each rubric is divided into three parts, corresponding to three major objectives that a successfully constructed environment should have:

1. Structure: Checks for basic directory structure, file presence, and environment variables.
2. Configuration: Asks the question "Is this configured?", checks for whether dependencies have been correctly configured.
3. Functionality: Asks the question "Is this usable?", runs actual tests to see if the functionalities are present.

There are many tests in each category, and their weights are adjusted based on their importance.

## Evaluation

Baseline Systems:

The study compared EnvAgent to two established automated code generation systems: one utilizing Anthropic’s advanced reasoning models and the other employing OpenAI’s code-focused models. These systems were chosen for their strong performance in creating software code and their prevalence in automated engineering processes. Both baselines were given full access to the target software repositories and complete details about the host system’s hardware.

Evaluation Metrics:

The performance of EnvAgent was assessed using three key metrics. These included the ability to create working environments, the quality of those environments, and a single combined score. Results showed EnvAgent significantly outperformed the baselines, achieving a 33.91% improvement in the final overall score – reaching 74.01, which was higher than the best baseline score of 30.10. This suggests EnvAgent produced both more functional environments and ensured greater accuracy through extensive testing.

## Conclusion

The process of creating the necessary software environments for code agents is a major hurdle in scaling up research and development. Currently, this task relies heavily on manual labor. To address this, a new system, ENVAGENT, was created to automatically build these environments using intelligent agents and by understanding dependencies. A new benchmark, ENVBENCH, was also developed to assess this system’s effectiveness. Preliminary results demonstrate a significant improvement – ENVAGENT achieved a 33.91% increase in success rates compared to existing automated agents, representing a substantial step towards more efficient and reproducible research.

# Thank you!

Autofill

;
20251105-Sam_Huang
