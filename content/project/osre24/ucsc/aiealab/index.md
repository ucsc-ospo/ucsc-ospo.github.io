---
title: "Artificial Intelligence Explainability Accountability"
authors: [lgilpin]
author_notes: ["Assistant Professor, UC Santa Cruz"]
tags: ["osre24", "uc", "AI/ML", "AI for education"]
date: 2024-02-07
lastmod: 2024-02-07
---

## Trustworthy Logical Reasoning Large Language Models (LLMs) {#trustworthy-logical-reasoning-large-language-models--llms}
 
Logical LLMs is a project to translate the output from large language models (LLM) into a logic-based programming language (prolog) to detect inconsistencies and hallucinations automatically .  The goals of this project would be to build a user interface for users to be able to give feedback which can be incorporated into the system.  The project goal is to create a trustworthy hybrid open-source LLM tool that can learn from user feedback and explain its mistakes.
 
 
### Collect Hallucinations and Facts {#collect-hallucinations-and-facts}
 
-   **Topics**: AI/ML, data collection, logic, user interfaces
-   **Skills**: javascript, html, python, bash, git
-   **Difficulty**: Easy/Moderate
-   **Size**: Large
-   **Mentors**: {{% mention lgilpin %}} (and a PhD student TBD).
 
 
### Specific Tasks {#specific-tasks}
 
-   Run queries in an LLM API with various prompts.
-   Create a user interface system that collects user feedback in a web
	browser.
-   Create a pipeline for storing the user data in a common format that
	can be shared in our database.
-   Document the tool for future maintenance.
 
 
## Explaining failures in autograding {#explaining-failures-in-autograding}
 
The eXplainable autograder (XAutograder) is a tool for autograding student coding assignments, while providing personalized explanations or feedback.  The goal of this project is to create an introductory set of coding assignment with explanations of wrong answers.  This benchmark suite will be used for testing our system.  The project goal is to create a dynamic autograding system that can learn from student's code and explain their mistakes
 
 
### Design introductory questions and explanations {#design-introductory-questions-and-explanations}
 
-   **Topics**: AI/ML, AI for education, XAI (Explainable AI\_
-   **Skills**: python, git
-   **Difficulty**: Moderate
-   **Size**: Large
-   **Mentors**: {{% mention lgilpin %}} (and a PhD student TBD).
 
 
### Specific Tasks {#specific-tasks}
 
-   Design 5-10 basic programming questions (aggregated from online,
	other courses, etc).
-   Create tests of correctness (unit tests), and a testing framework
	which can input a set of answers, and provide a final assessment
-   Create a set of baseline explanations for various error cases, e.g.,
	out of bounds error, syntax error, etc.
-   Create a pipeline for iterating on the test cases and/or explanation
	feedback.
-   Document the tool for future maintenance.

