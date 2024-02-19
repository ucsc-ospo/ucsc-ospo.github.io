---
title: "Automatic reproducibility of COMPSs experiments through the integration of RO-Crate in Chameleon" 
authors: [rsirvent]
author_notes: [Established Researcher at Barcelona Supercomputing Center]
tags: [osre24, reproducibility, provenance, RO-Crate, Chameleon, COMPSs]
date: 2024-02-19
lastmod: 2024-02-19
---

- **Topics:** 
- **Skills:** Python, JSON, Bash scripting, Linux, image creation and deployment
- **Difficulty:** Medium
- **Size:** Large (350 hours)
- **Mentors:** {{% mention rsirvent %}}

**Project Idea Description**

The [COMPSs programming model](https://compss.bsc.es/) provides an interface for the programming of a
sequential application that is transformed in a workflow that, thanks to the COMPSs runtime, is later
scheduled in the available computing resources. Programming is enabled for different languages through
the use of bindings: Java, C/C++ and Python (named PyCOMPSs).
COMPSs is able to generate [Workflow Provenance information](https://compss-doc.readthedocs.io/en/stable/Sections/05_Tools/04_Workflow_Provenance.html)
after the execution of an experiment. The generated artifact (code + data + recorded metadata) 
enables the sharing of results through the use of tools such as the [WorkflowHub portal](https://workflowhub.eu/), 
that provides the capacity of generating a DOI of the results to include them as permanent references 
in scientific papers.

The format of the metadata generated in COMPSs experiments follows the [RO-Crate specification](https://www.researchobject.org/ro-crate/), 
and, more specifically, two [profiles](https://www.researchobject.org/ro-crate/profiles.html): 
the Workflow and Workflow Run Crate profiles. This metadata enables not only the sharing of results, but also their
reproducibility.

This project proposes the creation of a service that enables the automatic reproducibility of COMPSs experiments
in the Chameleon infrastructure. The service will be able to get a COMPSs crate (artifact that follows the RO-Crate
specification), and, by parsing the available metadata, build a Chameleon compatible image for reproducing the
experiment in the testbed. Small modifications to the COMPSs RO-Crate are foreseen (i.e. the inclusion of third party
software required by the application).

**Project Deliverables**
- Study the different environments and specifications (COMPSs, RO-Crate, Chameleon, Trovi, ...).
- Design the most appropriate integration, considering all the elements involved.
- Integrate PyCOMPSs basic experiments reproducibility in Chameleon.
- Integrate PyCOMPSs complex experiments reproducibility in Chameleon (i.e. with third party software dependencies).




