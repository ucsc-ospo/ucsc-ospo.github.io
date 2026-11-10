---
title: "Final Report: From Lookup to Reasoning, an Allocation-Aware Resource Advisor for Chameleon"
subtitle: "Helping Chameleon's assistant answer \"what should I reserve, and for how long?\""
summary: "An advisor that uses live availability and real Trovi artifacts to recommend hardware and write python-chi reservations, along with a benchmark to measure whether it helps."
authors: [vivek-rai, marshalp]
tags: ["osre26", "reproducibility", "chameleon", "llm", "benchmark", "final-report"]
categories: ["osre26", "SoR"]
date: 2026-11-09
lastmod: 2026-11-09
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Chameleon testbed"
  focal_point: "Center"
  preview_only: true
---

Hello! I'm Vivek Rai, and this is my final report for my Summer of Reproducibility project on the [Chameleon](https://www.chameleoncloud.org/) testbed, under the mentorship of Paul Marshall. Since this is my only blog post for the project, I'll go over the whole thing here: the problem, how the system works, how I evaluated it, and what I learned along the way.

The code and benchmark are available at [github.com/Odysseus707/chameleon-advisor](https://github.com/Odysseus707/chameleon-advisor), and my final presentation slides are [here](final-presentation.pdf).

## Background

Chameleon is a testbed where researchers can reserve real hardware, from full bare-metal servers to small edge devices like Raspberry Pis and Jetsons (through CHI@Edge). Before running any experiment, a user has to figure out which device or node type to use, whether one is available, which image to run, and how long to reserve it for.

Chameleon already has a documentation chatbot that answers questions from the docs. However, it doesn't know what hardware exists or what is currently reserved, and it never looks at real experiments. So when I asked it a basic reservation question, this is what came back:

{{< figure src="before.png" caption="The deployed assistant before this project." >}}

The goal of my project was to change that. Given a workload described in plain language, the assistant should recommend hardware that can do the job, check that it is actually free, and give the user a reservation they can run.

## How the advisor works

The advisor sits behind the existing chatbot and only runs when the question is about resources. Everything else still goes through the normal documentation path.

{{< figure src="architecture.png" caption="How a question flows through the system." >}}

For a resource question, the advisor gathers information from four places:

- The **Reference API**, for hardware details like RAM, CPUs and GPUs.
- **Blazar**, Chameleon's reservation service, for what is available right now. This was especially important for edge devices, since the Reference API doesn't list any CHI@Edge hardware at all.
- A small **capability table** of published hardware specs, such as CUDA and tensor core counts.
- **Trovi artifacts**, which are experiments other researchers have published on Chameleon.

The model (Llama-3.3-70B, the same one the deployed chatbot uses) then reasons over this information and returns a recommended device or node type, a count and duration, python-chi code to make the reservation, and links to the artifacts it used. Here is the same question from before:

{{< figure src="after.png" caption="The same question with the advisor on." >}}

## Using artifacts as evidence

Trovi artifacts are a good record of what hardware real experiments use, so I wanted the advisor to learn from them. I went through 205 artifacts and kept the 96 whose code actually reserves hardware through a Chameleon API call.

The tricky part was how to ingest them. The documentation chatbot splits text into chunks and searches over them, which works well for docs. But most of an artifact is the experiment itself, and only a few lines actually reserve hardware. When those artifacts were chunked like regular text, the important lines got lost. Instead, I parse the code and pull out only the reservation calls along with the device type, image and duration, and store them as small tagged records.

{{< figure src="ingestion.png" caption="Docs are chunked as text, while artifacts are parsed into structured records." >}}

## Building a benchmark

To check whether any of this actually helps, I built a benchmark with two parts: 134 questions for edge devices and 136 for bare metal. Each part has questions that ask the model to write reservation code, and questions that ask it to choose the right hardware.

{{< figure src="benchmark.png" caption="The two parts of the benchmark." >}}

Each answer is graded by automated checks in five groups: whether it uses the right API calls (mechanism), the right values like site and duration (specifics), avoids calls that would break things (safety), picks hardware that is actually free (feasibility), and picks hardware that can do the job (capability). I kept these groups separate instead of combining them into one score, because a common mistake was getting all the values right but using the wrong reservation call, for example reserving a Raspberry Pi with the bare-metal call. One combined score would hide that.

## Results

**Artifacts help, mostly with writing the code.** When given the right artifact, fully correct answers went from 2% to 31% for the chatbot and from 13% to 40% for Claude. Most of the improvement was in mechanism and specifics, meaning the artifacts mostly teach how to write the reservation rather than which hardware to choose.

{{< figure src="artifact-experiment.png" caption="Results with and without the right artifact, edge questions." >}}

**The advisor helps with choosing hardware.** With the advisor turned on, capability went from 11% to 60% and feasibility went from 41% to 71%. In other words, the chatbot started recommending devices that could actually do the job and were free at the time of asking.

{{< figure src="advisor-edge.png" caption="Results with the advisor off and on, edge questions." >}}

A few other results stood out:

- When I separated the advisor's fixed rules from the model's reasoning, the rules accounted for most of the gain (44 of the 58 points on capability). I had expected the model to be doing most of the work.
- The results held up on bare metal, where fully correct answers went from 0 to 58 out of 136. Without any help, the model mostly suggested portal steps or OpenStack commands instead of python-chi.
- The advisor made things worse for hardware that no artifact covers. Capability dropped from 45% to 21% on those questions.

{{< figure src="coverage.png" caption="Capability results based on how well the artifacts cover the requested hardware." >}}

That last result came down to the data. None of the artifacts I found document any of the accelerators on CHI@Edge, like the Jetsons or Coral boards. So the advisor can only be as good as the experiments people have shared.

## Challenges

There were quite a few things that didn't go as planned:

- **Missing edge data.** The Reference API lists no CHI@Edge devices, and the first version of the integration was also returning no edge availability. I switched to reading this directly from Blazar.
- **Model size.** I started with Qwen2.5-32B running on a Chameleon node. It barely improved with the extra context, while the 70B model improved a lot. When that node also became unavailable, I moved to Llama-3.3-70B on TACC.
- **Chunking artifacts.** My first approach treated artifacts like documentation, which didn't work and led to the code-parsing approach above.
- **Measuring the right thing.** My first benchmark only checked whether the code was correct. I later realized the harder part is choosing the hardware, so I added the hardware-choice questions and the bare-metal set.

## Future work

There are a few directions I'd like to see this go next:

- Letting the assistant make the reservation directly after the user confirms, instead of just giving code.
- Hosting the service in production, which needs its own credentials.
- Improving retrieval. Right now the correct artifact only shows up in the top 3 results about a third of the time.
- Getting more artifacts that cover edge accelerators, since that is where the advisor struggles most.

## Acknowledgements

This project taught me a lot about how much of research is about measuring things carefully. Several of my early assumptions only turned out to be wrong once I had an experiment that could test them. I'd like to thank my mentor Paul Marshall for his detailed feedback and guidance throughout the summer, Kate Keahey for her questions and input on reproducibility artifacts, and the UC Santa Cruz OSPO team for running this program.
