---
title: "Mid-term blog post for Public Artifact Data and Visualization"
subtitle: ""
summary: ""
authors: [zjyhhhhh, Roasters05]
tags: ["osre23", reproducibility]
categories: [SoR'23]
date: 2023-07-31
lastmod: 2023-07-31
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

Over the past few weeks, our platform development has been progressing steadily, and we are excited to share the milestones we have achieved so far. As planned in our [introductory blog](/report/osre23/intel/artifactviz/20230617-zjyhhhhh), we have successfully laid the groundwork for the platform with the guidance and support of our mentor.

## Milestones and Accomplishments

Here are some of the key functionalities we have implemented so far:

1. Modular Architecture: We successfully designed the platform with a modular architecture, separating the Graphical User Interface (GUI) and Command-Line Interface (CLI) functionalities. This modularity allows users to interact with the platform in their preferred way.
2. Experiment and Bucket Creation: Users can now create experiments, buckets (for storing different implementations of experiments), and iterations using either the GUI or CLI.
3. Real-time Backend Environment Monitoring: Through the command line interface, users have the capability to control the monitoring of backend environment data, allowing for real-time tracking and analysis of important metrics.
4. Visualizing Environment Variables: Users can now visualize detected environment variables on the platform. Moreover, they can compare iterations within different buckets and gain more insights by observing the timeseries data, such as CPU usage, in a graphical format.

## Challenges

In the early stages of designing our platform, we encountered significant challenges at the system design level. One of the most daunting obstacles we faced was devising an effective method to monitor backend environment variables. To tackle this obstacle, we engaged in extensive discussions and sought guidance from our mentor. After careful consideration, we decided to adopt a multi-process approach to monitor the backend environment variables effectively. Specifically, we devised a meticulous strategy of creating a separate process in the background for each specific metric we needed to monitor. By allocating a dedicated process to each metric, we ensured a streamlined and efficient monitoring process.

Currently, we are facing a challenge related to monitoring metrics. Since different users have varying monitoring requirements, it is impractical for us to manually write monitoring solutions for each user. To address this issue, we are actively working on implementing a pluggable design that allows users to configure their own monitoring preferences.

Our approach involves providing users with the flexibility to define their custom configuration files or write monitoring programs following our documented guidelines. This way, users can specify the specific metrics they wish to monitor and tailor the monitoring process to their individual needs.

## Try it Out!

As mentioned earlier, we have completed the core functionalities of our platform, and we would love to have you try it out and provide us with valuable feedback. Here are the links to our repositories where you can explore and experiment with our platform:

1. [GUI Repository](https://github.com/PublicExperimentDatabase/PublicExperimentGUI) and [CLI Repository](https://github.com/PublicExperimentDatabase/PublicExperimentCLI)
   - In the README.md file of GUI repo, you will find detailed installation instructions to set up the Graphical User Interface (GUI). Follow the steps provided to get started with our platform.
2. [Sample Repository](https://github.com/PublicExperimentDatabase/test-experiment)
   - In this repository, we have included scripts that allow you to run our program. Additionally, you can use these scripts as templates to monitor your own programs according to your specific requirements.

We welcome you to take the platform for a test drive and feel free to raise any issues you encounter during the installation process. Your feedback is invaluable to us, as it helps us identify and address any potential installation challenges and improve the user experience.
