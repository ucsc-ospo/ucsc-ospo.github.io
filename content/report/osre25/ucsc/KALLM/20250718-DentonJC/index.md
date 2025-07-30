---
title: "Midterm Report: KAN Integration into LLMs"
subtitle: ""
summary: "Testing KANs in a language model to see if math-driven layers can do more with less."
authors: 
  - DentonJC
tags: ["osre25"]
categories: ["machine-learning"]
date: 2025-07-18
lastmod: 2025-07-27
featured: false
draft: false

---

Imagine if we could make neural networks that are not just more efficient, but smarter in how they learn. That’s the promise behind **Kolmogorov–Arnold Networks** (KANs)—a fascinating new architecture that replaces the usual "weighted sums and activation functions" with more mathematical finesse. Instead of processing all inputs in one big lump, KANs treat each input dimension individually, transforming them with elegant functions like B-splines or simpler polynomials. The idea is simple but powerful: do more with less.

For my project, I set out to explore what happens when we integrate these KAN layers into a lightweight language model called **SmolLM2**, training and testing it on a **smol-smoltalk** dataset.

## Setting the Stage: SmolLM2 Meets KAN

The original SmolLM2 has 135 million parameters and 30 transformer blocks—plenty of moving parts. To keep things manageable during the initial phase, I created a mini version of the model with just 3 blocks and a trimmed-down vocabulary. This setup let me test dozens of KAN variations quickly, using a simple text classification task (AGNews) as a playground before moving on to full-scale language modeling.

Despite working with a simplified model, I managed to successfully train a full 30-block KAN-based SmolLM2. That model even passed challenging language benchmarks with flying colors—matching the performance of the original, linear-layer version. That's a big win.

## What Worked (and What Didn't)

Along the way, I tried out a variety of KAN flavors: spline-based, radial basis functions (RBF), rational functions, and no fewer than eight types of orthogonal polynomials—like Chebyshev, Legendre, and Hermite. Each one brings its own quirks, strengths, and training times. 

Some key takeaways:

- **Chebyshev (second kind)** with a low polynomial degree (just 2!) delivered the best speed/accuracy trade-off.
- **Jacobi** and **Gegenbauer** polynomials edged slightly ahead in raw accuracy but required much longer training times.
- Replacing each linear layer with a KAN version (keeping parameter count similar) worked fine—but layering them in parallel or sequence didn’t add much.
- A baseline with regular linear layers still performed slightly better (60.8% vs. 60.3%), but KANs showed they can come close with room for optimization.

## Why This Matters

What’s compelling is not just that KANs *can* work, but that they bring some appealing properties:

- **Parameter efficiency**: Good performance with fewer or similarly-sized layers.
- **Flexibility**: They adapt well to existing hyperparameters—less fine-tuning needed.
- **Stability**: They run smoothly in fp16 (a lower-precision format), which is critical for efficient training.
- **Potential for richer activations**: Some existing projects still rely on activations like ReLU or SiLU alongside KANs. But I found KANs alone could learn well without them, opening up more dynamic architectures in the future.

## What's Next

With the heavy lifting done, code written, models trained, ideas tested, the remainder of the project is focused on refinement. That means more training on generative tasks, better tuning of polynomial degrees, smarter initialization strategies, and potentially making KAN-based layers more plug-and-play.

The fact that a fully KAN-powered SmolLM2 can hold its own on tough language benchmarks is more than just a proof of concept. It’s a hint that we might not have to keep scaling models indefinitely to get better performance. Instead, we can get more from each parameter, by changing how the model *thinks*.
