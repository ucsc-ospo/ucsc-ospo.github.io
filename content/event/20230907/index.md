---
title: 'Adam Kennedy (Voltron Data): Polygraph'

event: 'Eusocial Interest Group Meeting'
#event_url: https://example.org

location: University of California, Santa Cruz
address:
  street: 1156 High St
  city: Santa Cruz
  region: CA
  postcode: '95064'
  country: United States

summary: Adam Kennedy (Voltron Data) is speaking about Polygraph, a new effort to make processing and optimizations of query plans more efficient
abstract: ''

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2023-09-07T14:00:00-0700'
date_end: '2023-09-07T15:00:00-0700'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2023-09-06'

authors: [adam.kennedy]
tags: []

# Is this a featured talk? (true/false)
featured: false

image:
  caption: ''
  focal_point: Right

url_code: ''
url_pdf: ''
url_slides: ''
url_video: 'https://www.icloud.com/iclouddrive/0920UPOGUXIosE6viyjHJe6BQ#video1862580471'

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides:

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
---

{{% callout note %}}
This is an expanded version of Adam Kennedy's presentation at the [2nd International Workshop on Composable Data Management Systems 2023 (CDMS)](https://ceur-ws.org/Vol-3462/CDMS0.pdf) ([agenda](https://ceur-ws.org/Vol-3462)). The following abstract is copied from [there]((https://ceur-ws.org/Vol-3462/CDMS12.pdf)).
{{% /callout %}}

The maturity and substantial investment in Apache Calcite establish it as the open source standard for query planning and
optimization across numerous data tools. Nevertheless, utilizing Apache Calcite for dynamic query planning in a diverse tool
stack with multiple languages has proven challenging. Through the integration of Apache Arrow, we introduce Polygraph:
a language-independent, parse-free, and efficient format for query plans. Its purpose is to enhance plan interoperability,
diminish latency and overheads, and facilitate dynamic query optimization. This experimental format allows for the efficient
exchange of query plans between tools in diverse languages with minimal serialization overhead.  

While future query engines are steering away from Java, Calcite remains the solitary mature option for query planning
across a broad spectrum of workloads. Few alternatives come close to matching its features. However, Calcite relies on
tree-based JSON or XML plan representations that do not readily lend themselves to certain optimizations and necessitate
substantial overhead for serialization, I/O, and parsing. The commingling of planners and engines across languages is rare,
unusual, and complex. Such approaches typically result in ad hoc, internal formats with limited reusability. Addressing
these challenges, Polygraph relocates the query plan to Arrow. Polygraph employs a graph structure encoded with columnar
storage techniques. Preliminary experiments indicate an order of magnitude reduction in query plan size compared to JSON
encoding, without incurring copying and serialization overheads. Arrow provides zero-copy, shared-memory, and parse-free
capabilities, along with fast RPC via Arrow Flight. In this representation, plan consumers only need to load the components
and properties of a query plan required for a given computation. These efficiencies substantially reduce the latency between
plan generation and query execution. Moreover, we envision significant potential for other advancements, including resource
planning, ML preprocessing, and integration into ML training and inference.  

Until recently, there was no urgent imperative to represent query plans efficiently. However, the escalating complexity
and size of query graphs will persist as data tools become more deeply integrated into intricate ML workloads. Polygraph’s
agile and decomposable graph representation empowers data engines to contribute to query optimization and resource
management. Enhanced integration with top-tier ML systems becomes more viable, facilitating the incorporation of run-time
compute planning and resource management into the query plan, utilizing tools like Apache Acero. The benefits extend
beyond improvements in space efficiency and latency. Query sub-plans can be optimized in-situ using real-time hardware
metrics. Value relations and broadcast tables can be seamlessly embedded in the plan as Arrow objects, accessed in a zero-copy
manner. Large models can be directly incorporated into the query plan, incurring no loading cost until required. Increased
investment in query plan representations, exemplified by Polygraph, supports the data community in keeping pace with
advancements in new architectures and problem domains, such as AI.

