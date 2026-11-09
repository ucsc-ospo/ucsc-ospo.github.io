---
title: "Final Report: From Lookup to Reasoning, an Allocation-Aware Resource Advisor for Chameleon"
summary: "Teaching the Chameleon assistant to answer \"what should I reserve, and for how long?\" using live availability and real Trovi artifacts, plus a benchmark to check whether it actually helps."
authors: [vivek-rai, marshalp]
tags: ["osre26", "reproducibility", "chameleon", "llm", "final-report"]
categories: ["osre26", "SoR"]
date: 2026-11-09
lastmod: 2026-11-09
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "The advisor answering a CHI@Edge camera question with live availability and a ready-to-run reservation"
  focal_point: "Top"
  preview_only: true
---

Hello! I'm Vivek Rai, and this is my final report for my Summer of Reproducibility project on the [Chameleon](https://www.chameleoncloud.org/) testbed, under the mentorship of Paul Marshall. Over the summer I worked on getting Chameleon's assistant to do something it couldn't before: tell a researcher what hardware to reserve for their workload, check that it's actually free, and hand them a reservation that runs.

## Background

Every experiment on Chameleon starts with the same few decisions before any science happens: which node or device type, whether one is free, which image, how the lease connects to the container or server, and for how long. Chameleon already has a documentation assistant that answers questions from the docs, and it does that well. But it has no view of the hardware or of current reservations, so when you ask it something like this, it has nothing to say:

{{< figure src="before.png" caption="The deployed assistant before this project." >}}

## What I built

**An advisor with live state.** It reads hardware details from Chameleon's Reference API, current availability straight from Blazar (the reference API lists zero CHI@Edge devices, so Blazar is the only way to see edge hardware), and a small capability table of published specs. It only kicks in on resource questions, everything else still goes through the normal docs path.

**Artifacts as evidence.** Trovi holds the experiments people have actually run on Chameleon, which makes it the best record of what hardware real workloads use. I went through 205 artifacts and ingested the 96 whose code really reserves hardware. Since only a few lines of an artifact do the provisioning, I parse those calls out of the code instead of chunking the whole thing as text, which turned out to be the difference between useful grounding and noise.

**A two-wing benchmark.** 134 edge items and 136 bare-metal items, each answer graded by automated checks for whether the code uses the right calls, the right values, avoids unsafe calls, picks hardware that's free, and picks hardware that can do the job. These are never averaged into one score, since the most common failure is getting every value right and still using the wrong reservation call.

Here's the same question with the advisor on:

{{< figure src="after.png" caption="Same question, advisor on: a free device, why it fits, and runnable python-chi." >}}

## What I found

Giving the model the right artifact took fully correct answers from 2% to 31% for the chatbot (and 13% to 40% for Claude). Adding the advisor on top is what fixed hardware choice: picking a device that can do the job went from 11% to 60%, and picking one that's actually free went from 41% to 71%. The same pattern held on bare metal. One surprise was that most of the gain came from fixed rules in the advisor, not from the 70B model reasoning over them.

The most useful result was a failure, though. When the question is about hardware no artifact covers, the advisor makes things worse:

{{< figure src="coverage.png" caption="Grounding helps only where the artifact corpus covers the hardware." >}}

Not one artifact on Trovi documents a CHI@Edge accelerator (the Jetsons or Coral boards). So the assistant is only as good as the experiments people have published, which is a nice argument for publishing more of them.

Along the way I also had to reroute a few times. The first model I used (Qwen2.5-32B) barely benefited from the extra context, so I moved to Llama-3.3-70B, which is what the deployed system runs anyway. The first benchmark only scored whether the code was correct, which missed the hard part (deciding what to reserve), so I rebuilt it around that.

## Deliverables

- The advisor and both benchmark wings: [github.com/Odysseus707/chameleon-advisor](https://github.com/Odysseus707/chameleon-advisor)
- Final review slides with the full results: [final-presentation.pdf](final-presentation.pdf)
- The benchmark also packages as a pip-installable wheel (still being tested)

## Next Steps

1. **Actually reserve the node**, with one confirmation instead of copy-pasting code.
2. **Production hosting**, which needs its own credentials since it can't act with each user's login.
3. **Better retrieval.** The right artifact only shows up in the top 3 about a third of the time.

## Reflection

The biggest thing I learned is how much of research is measurement. A lot of my early assumptions, like the bigger model doing the heavy lifting, only fell apart once I set up an experiment that could isolate them. Thank you to Paul Marshall for the honest, detailed feedback all summer, to Kate Keahey for her questions about reproducibility artifacts, and to the UC Santa Cruz OSPO team for running the program.
