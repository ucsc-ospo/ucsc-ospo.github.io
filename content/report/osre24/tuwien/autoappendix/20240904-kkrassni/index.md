---
title: "AutoAppendix: Towards One-Click reproducibility of high-performance computing experiments"
authors: [kkrassni]
tags: ["osre24", "sc24", "chameleon", "reproducibility"]
categories: [SoR]
date: 2024-09-04
lastmod: 2024-09-04
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

# AutoAppendix: Towards One-Click reproducibility of high-performance computing experiments

Hi everyone,

I'm excited to wrap up the AutoAppendix project with our final findings and
insights. Over the course of this initiative, we’ve worked to assess the
reproducibility of artifacts submitted to the SC24 conference and create
guidelines that aim to improve the standard for reproducible experiments in the
future. Here's a summary of the project's final phase and what we’ve learned.

## Project Goals and Progress

The goal of AutoAppendix was to evaluate the computational artifacts provided by
SC24 paper submissions, focusing on reproducibility. These artifacts accompany
papers applying for the "Artifact Replicable" badge in the conference's
reproducibility initiative. Volunteer members of this initiative assess 1-2 paper appendices each. In this project, we analyzed a larger portion of artifacts to gain a broader perspective on potential improvements to the reproducibility process.

We selected 18 out of 45 submissions, focusing on experiments that could be
easily replicated on Chameleon Cloud. Our evaluation criteria were based on
simplicity (single-node setups) and availability of resources. The final
analysis expanded on the earlier midterm findings, shedding light on various
challenges and best practices related to artifact reproducibility.

## Artifact Evaluation Process

During the evaluation process, we focused on examining the completeness and
clarity of the provided artifacts, looking closely at documentation, setup
instructions, and the degree of automation. 

Our first step was to replicate the environments used in the original
experiments as closely as possible using the resources from Chameleon. Many papers included instructions for creating the necessary software environments,
but the clarity of these instructions varied significantly across submissions.
In some cases, we even encountered challenges in reproducing results due to unclear
instructions or missing dependencies, which reinforced the need for
standardized, clear documentation as part of the artifact submission process.

We observed that *containerization* and *semi-automated setups* (with scripts
that break down the experiment into smaller steps) were particularly effective
in enhancing the reproducibility of the artifacts. One artifact
particularly caught our attention due to its usage of the Chameleon JupyterHub
platform, making it reproducible with a *single click*. This highlighted the
potential for
streamlining the reproducibility process and showcased that, with sufficient
effort and the right tools, experiments can indeed be made replicable by
*anyone*.

## Results

Throughout the evaluation, we observed that reproducibility could vary widely
based on the clarity and completeness of the documentation and the automation of
setup procedures. Artifacts that were structured with clear, detailed steps for
installation and execution tended to perform well in terms of replicability.

From our evaluation, we derived a set of guidelines (intended as must-haves) and
best practices (recommended) for artifact reproducibility, which can be found below.

Due to our fascination of the potential of the Chameleon JupyterHub platform and its adjacent [Trovi](https://www.chameleoncloud.org/experiment/share/) artifact repository, we decided to create
several templates that can be used as a starting point for authors to make integration
of their artifacts with the platform easier. In the design of these templates,
we made sure that artifacts structured according to our guidelines are
particularly easy to integrate.

### Guidelines

1. **Clear Documentation**: Provide clear and detailed documentation for the artifact in the corresponding appendix, such that the artifact can be replicated without the need for additional information. For third-party software, it is acceptable to refer to the official documentation.
   
2. **Software Setup**: Clearly specify the versions of all (necessary) software components used
in the creation of the artifact. This includes the operating system, libraries, and tools.
Particularly, state all software setup steps to replicate the software environment

3. **Hardware Specifications**: Specify the hardware the experiment was conducted on. Importantly,
state the architecture the experiments are intended to run on, and ensure that
provided software (e.g. docker images) are compatible with commonly available
architectures.

4. **Expected Results**: Always provide the expected outputs of the experiment, especially when run on different hardware, to make it easier for reviewers to assess the success of the replication.

5. **Public Data**: Publish the experiment data to a public repository, and make
sure the data is available for download to reviewers and readers, especially during
the evaluation period. Zenodo is a recommended repository for this purpose.

6. **Automated Reproducibility**: For long-running experiments, provide
progress output to the reviewer to ensure the experiment is running as expected.
Give an idea in the documentation of
- how much time long-running steps in the reproduction will take
- what the progress output looks like or how frequently it is emitted

7. **Sample Execution**: Conduct a sample evaluation with hardware and software
as similar as possible to the intended reproduction environment.

### Best Practices

1. **Reproduciible Environment**:
Use a reproducible environment for the artifact. This can come in several forms:
  - **Containerization**: Provide instructions for building the environment, or,
  ideally, provide a ready-to-use image. For example, Docker, Signularity or VirtualBox images can be used for this purpose
  - **Reproducible Builds**: Package managers like [Nix](https://nixos.org/) or [Guix](https://guix.gnu.org/) have recently spiked in popularity and allow their users to create reproducible environments, matching the exact software versions across different systems.

2. **Partial Automation**: It often makes sense to break an experiment down into
smaller, more manageable steps. For Linux-based systems, bash scripts are particularly viable for this purpose. We recommend prefixing the scripts for each step with
a number, such that the order of execution is clear.

3. **X11 Availability**: Usually, reviewers will not have access to a graphical user
interface on the system where the artifact is evaluated. If the artifact requires a
graphical user interface, provide a way to run the artifact without it. For example,
save `matplotlib` plots to disk instead of showing them with `plt.show()`.

4. **Experiment output**: Do not provide output files of the experiment in your artifact,
unless explicitly intended. If provided output files are intended for comparison,
they should be marked as such (e.g. in their filename). Similarly, any output logs
or interactive outputs in Jupyter notebook should not be part of the artifact, but
rather be initially generate during the artifact evaluation.

### Trovi Templates

Our templates share a common base that features
a *central configuration file* for modifying the
Chameleon experiment parameters (such as node type). Building on this base, we provide three templates with sample experiments that each use different environments:

- **Docker template**: This template is designed for containerized experiments and supports nvidia GPUs over the `nvidia-container-toolkit` integration. 
- **Nix template**: Sets up the Nix package manager with a `shell.nix` file that can be used to configure the environment.
- **Guix template**: Installs the Guix package manager and executes a sample experiment from an existing reproducible paper that hinges on the reproducibility of the software environment.

## Conclusion

In summary, the AutoAppendix project has been an insightful journey into the
complexities of artifact reproducibility. Our evaluations highlight both the
challenges and potential solutions for future reproducibility initiatives. By
following these essential guidelines and implementing best practices, we aim for the
research community to achieve higher standards of transparency and reliability
in scientific research and help to ensure that the results of experiments can be replicated by others.

Thanks for following along with our progress! We’re excited to see the positive
impact these findings will have on the research community.

If you are interested in the full project report, you can find it [here](https://drive.google.com/drive/folders/113OsxGAlfyvlJnvpH5zL2XD-8gE3CYyu?usp=sharing), together with the *Trovi* templates.