---
title: "[FLASHNET]: Leveraging ML-augmented I/O in Linux"
subtitle: ""
summary: ""
authors: ["Justin08784"]
author_notes: ["Student at the University of Chicago"]
tags: ["osre23", reproducibility]
categories: [SoR'23]
date: 2023-08-02
lastmod: 2023-08-02
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

Hello everyone,

This is my second blog post for SoR 2023. As you may recall from my [initial blogpost](/report/osre23/uchicago/flashnet/20230530-Justin08784), I am working on the [Flashnet](/report/osre23/uchicago/flashnet/) project under the mentorship of {{% mention haryadi %}}.

I've been assigned two major tasks under Flashnet:
1. Perform post-training quantization (PTQ) on existing Flashnet models 
2. Implement a rocksDB client (to interface with the Flashnet kernel) with 3-way replication

## Task 1: Perform post-training quantization (PTQ) on existing Flashnet models 
Since all of our models are currently built using the keras API, I decided to use the tensorflow-lite library, which supports direct conversion. Unfortunately, I encountered several persistent bugs while attempting to apply full-integer quantization on our binary neural network model:

### Shape/dimension distortion:
Bug description: The quantized tflite model produces outputs of shape (8, 1) –– same as input shape–– when the original model produces single-value outputs (1, 1).

Status: Resolved
- The original model has an input dimension of 8 for each input/x-value and there could be several inputs grouped in a single batch. 
- Input/batch size is also determined implicitly in the normalization layer of the original model
- However, the "interpreter" in the quantized model runs inference one by one, and so batch size needs to be explicitly set to "1" i.e. a shape of single input, (1,8)
- Doing so resolves the model distortion


### Incorrect y-value range: 
Bug description: There are no variation in the quantized model outputs (i.e. it spits out the same value for each input row)

In the original model, each inference output is a floating point value between 0 and 1. Outputs also vary according to input. This output is rounded towards 0 or 1 using a 0.5 standard cutoff (i.e. x > 0.5 → x = 1). Since the quantized model condenses 32-bit floats into 8-bit integers, we should expect a similar variation in output values across an 8-bit integer range.

Printing the quantized model weights, I discovered that weight burst/exploding gradient may be occur during quantization process i.e. the values of weights are exploding to infinity or vanishing to 0, and therefore unable to deliver any meaningful value. The likely consequence of this is that the inference output always equals the bias matrix (since the Wx term in y = Wx + B gets zeroed out). 

Status: Open 
- Multiple potential causes were considered, without any success:
    - Improper quantization of inputs/outputs
    - Insufficient training time/number of epochs
    - Incompatible model type/structure
    - Incompatible tensorflow-lite version
- At this point, I concluded that tensorflow-lite is too bug-ridden to make making any further attempts with the library not worthwhile.


## Task 2: Implement a rocksDB client (to interface with the Flashnet kernel) with 3-way replication
rocksdb is an embedded database for key-value data. Our Flashnet team is currently implementing a Flashnet client in ceph, and so they have tasked me to explore an implementation in rocksdb as an alternative.

I've started on this segment of the project only recently, so my current work is still in its formative stages. As of writing, I've been primarily concerned with setup of software (on a new chameleon instance), running toy db examples, and educating myself on basic terminology/rocksdb documentation.


## Future work
I expect to continue working on Task 1 (do quantization from ground-up or use a different library) and Task 2 as detailed above. I also hope to implement a transformer-based model to supplement our existing suite of Flashnet models.

















