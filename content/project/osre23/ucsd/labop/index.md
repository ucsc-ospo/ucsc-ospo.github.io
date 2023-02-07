---
title: LabOP - an open specification for laboratory protocols, that solves common interchange problems stemming from variations in  scale, labware, instruments, and automation.
authors: ["Timothy Fallon", "Dan Bryce"]
author_notes: 
- "NIH NRSA F32 Postdoctoral Fellow - Scripps Institution of Oceanography, UC San Diego"
- "Fellow - Smart Information Flow Technology"
tags: ["osre23", "ucsd", "uc", "biology","chemistry","laboratory automation", "reproducibility"]
date: 2023-02-06
lastmod: 2023-02-06
---

<!---
Instructions for project submission here: https://ospo.ucsc.edu/osredocs/formentors/

All the projects so far:
https://ospo.ucsc.edu/osre/#projects

-->

### Project idea 1: Software, hardware, and wetware building LabOP with simultaneous language & protocol development & test executions

- **Topics:**  Software standard development, Laboratory automation, Biology   
- **Skills:** Python, Semantic Web Technologies (RDF, OWL), interest to think about describing biological & chemical laboratory processes
- **Difficulty:** Moderate
- **Size:** 400 hours
- **Mentors:**
	1. [Tim Fallon (UCSD)](mailto:tfallon@ucsd.edu){{% mention "photocyte" %}}
	2. [Dan Bryce (SIFT)](mailto:dbryce@sift.net){{% mention "danbryce" %}}

---

#### About: The Laboratory Open Protocol Language (LabOP)

**See link: [https://bioprotocols.github.io/labop/](https://bioprotocols.github.io/labop/)**


LabOP is an *open* specification for laboratory protocols, that solves common interchange problems stemming from variations in scale, 
labware, instruments, and automation. LabOP was built from the ground-up to support protocol interchange.  It provides an extensible 
library of protocol primitives that capture the control and data flow needed for simple calibration and culturing protocols to 
industrial control.

##### Software Ecosystem

LabOP's rich representation underpins an ecosystem of several powerful software tools, including:

- [labop](https://www.github.com/bioprotocols/labop): the Python LabOP library, which supports:
  - *Programming* LabOP protocols in Python,
  - *Serialization* of LabOP protocols conforming to the LabOP RDF specification,
  - *Execution* in the native LabOP semantics (rooted in the UML activity model),
  - *Specialization* of protocols to 3rd-party protocol formats (including Autoprotocol, OpenTrons, and human readible formats), and
  - *Integration* with instruments (including OpenTrons OT2, Echo, and SiLA-based automation).
- [laboped](https://www.github.com/bioprotocols/laboped): the web-based LabOP Editor, which supports:
  - *Programming* LabOP protocols quickly with low-code visual scripts,
  - *Storing* protocols on the cloud,
  - *Exporting* protocol specializations for use in other execution frameworks,

#### About the Bioprotocols Working Group

The Bioprotocols Working Group is an open community organization developing a free and open standard for representation of biological 
protocols. 

To join the Bioprotocols Working Group:

- Join the community mailing list at: [https://groups.google.com/g/bioprotocols](https://groups.google.com/g/bioprotocols)
- Join the `#collab-bioprotocols` channel on the [Bits in Bio](https://bitsinbio.org/) Slack.

##### Leadership

_Elected Term: August 24th, 2022 - August 23rd, 2023_

**Chair:** [Dan Bryce (SIFT)](mailto:dbryce@sift.net)

**Finance Committee:**

- [Jeremy Cahill (Metamer Labs)](mailto:jeremy.cahill@metamerlabs.io)
- [Mark Doerr (University of Greifswald)](mailto:mark.doerr@uni-greifswald.de)
- [Tim Fallon (UCSD)](mailto:tfallon@ucsd.edu)


##### Governance
_Approved by community vote on August 16th, 2022_

**[https://bioprotocols.github.io/labop/about#Governance](https://bioprotocols.github.io/labop/about#Governance)**

##### Mission: 

The Bioprotocols Working Group is an open community organization developing free and open standards for representation of biological 
protocols. In support of that goal, the organization also develops tools and practices and works with other organizations to 
facilitate dissemination and adoption of these standards.

As an organization, the Bioprotocols Working Group holds the following values:

- The standards developed by the community should be available under permissive free and open licenses.
- Technical decisions of the community should be made following open and inclusive processes.
- The community is strengthened by fostering a culture of diversity and inclusion, in which all constructive participants feel 
comfortable making their voices heard.

