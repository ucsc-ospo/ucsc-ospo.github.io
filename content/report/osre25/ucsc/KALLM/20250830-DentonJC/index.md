---
title: "Wrapping Up KALLM"
subtitle: ""
summary: "The KANs are successfully reducing the number of weights required to achieve the same performance as the original model."
authors: 
  - DentonJC
tags: ["osre25"]
categories: ["machine-learning"]
date: 2025-09-03
lastmod: 2025-09-03
featured: false
draft: false
---

Large language models today look complicated, but if you peel back the layers, most of what you see is old technology: stacks of linear transformations. The Transformer architecture, the engine behind GPTs and their cousins, is often described as revolutionary. Yet the majority of its parameters are standard linear layers, the same kind of matrix multiplications you would find in a simple multilayer perceptron from the 1980s. For years these layers have gone unchallenged. They are fast, they scale, and they work. But maybe the time has come to ask: *can we do better than linear?*

This project explored exactly that. Instead of leaving those layers untouched, we tried replacing them with a more mathematically structured alternative: **Kolmogorov–Arnold Networks (KANs)**. The result is a working language model—SmolLM2, a 135-million-parameter Transformer—where the final feedforward blocks no longer consist of brute-force linear weights, but of compact polynomial-based functions. And the striking fact is that performance remained within the baseline range. Smaller KANs managed to match larger linear layers, showing that smarter mathematics can stand shoulder to shoulder with the workhorse of deep learning.


## Transformers

To understand the significance, let’s revisit what a Transformer actually is.  
A Transformer block has two main components: attention and feedforward. The attention mechanism computes how each word in a sentence relates to every other word. That is the clever part, and it is what made Transformers famous. But once attention finishes its work, the output is passed into a feedforward network. And this feedforward network is essentially two large linear layers, stacked with a nonlinearity between them.

Now stacking thirty such blocks yields a complete model like SmolLM2. Look at the parameter counts and you see a pattern: attention is not the main consumer. It’s the feedforward layers. They dominate memory and computation, making them the primary target for efficiency gains.


## What Are Kolmogorov–Arnold Networks?

So what happens if, instead of a giant matrix multiplication, we try something more structured? Enter Kolmogorov–Arnold Networks.

KANs are built on a mathematical theorem from the mid-20th century, which proved that any multivariate function can be decomposed into sums of univariate functions. Instead of mixing all inputs together at once, you treat each input dimension separately, applying a small nonlinear function, and then recombine. The beauty is that these univariate functions can be simple but expressive—like splines or polynomials—and yet, when summed, they approximate very complex mappings.

Think of a KAN layer as a set of individual univariate modules. Each one takes a single variable, bends it according to a chosen basis (polynomials, splines, etc.), and then all those bent versions are added up to produce the output. The richness of the final function depends on two factors:

- **Choice of basis**: You can bend with Chebyshev polynomials, with Legendre polynomials, with B-splines, or with other families.  
- **Degree**: This is how many bends you allow. A degree-1 polynomial is just a line. Degree-2 can capture curves. Higher degrees capture higher-order oscillatory components.

A Chebyshev polynomial of the second kind, degree 2, is one such basis. Unlike a simple quadratic, it has roots and oscillations that make it particularly good at spanning function space efficiently. This efficiency explains its favorable performance in our experiments: low degree means fewer parameters, but Chebyshev’s properties let it approximate more than you might expect from so few numbers.


## Why Small Can Beat Big

Linear layers require many parameters because they treat every input–output mapping as arbitrary. KANs assume smoothness: each input passes through a compact polynomial basis before recombination. This structure captures useful patterns with fewer parameters.

A degree-2 Chebyshev basis, for example, encodes curvature and oscillation efficiently. While a linear layer of the same size must spend parameters to approximate these effects, the polynomial basis includes them inherently. The result is comparable expressivity with fewer parameters. In language tasks where patterns are often smooth or compositional, this structured efficiency translates into competitive accuracy at lower cost.


## Baselines, Modifications, and Comparisons

Here’s what we actually tested, in plain language:

1. **The untouched baseline**: a pretrained SmolLM2, with all thirty blocks intact.  
2. **Linear restart**: the same pretrained model, but the last five feedforward modules were thrown away and replaced with freshly initialized linear ones. These then had to be trained again.  
3. **KAN replacement**: again, take the pretrained model, cut off the last five feedforward modules, and put in new KAN modules instead—specifically, Chebyshev of the second kind, degree 2.

In all three cases, the backbone of the model—the embeddings, the attention layers, and the first twenty-five blocks—was left untouched. Only the tail was modified. This design allowed us to test transfer learning: would the pretrained parts of the model still play nicely with the new pieces? The answer is yes. The attention layers and other linear projections adapted seamlessly, proving that KANs can be swapped in without destabilizing the whole system.

Training was done on **smol-smoltalk** dataset, a small-scale dialogue corpus used for both pretraining and fine-tuning. After training, all models were evaluated on the same subset of **BIG-Bench Hard** tasks.

<!--
## How Evaluation Works

The evaluation was not a casual check; it mirrored the structure of the Open LLM Leaderboard, but focused only on the core tasks relevant to dialogue and reasoning (since our training data did not include STEM problems, for example). Each task consists of prompts with clear expected answers: multiple choice, classification, or reasoning questions.

To evaluate, each model is placed in a simulated conversation. The prompt is fed in, the model generates a response, and that response is parsed. If the task is multiple choice, the evaluation extracts which option the model chose, checking against the gold label. If the task is free-form, the answer is normalized—lowercased, punctuation stripped, articles removed—so that small differences in formatting do not count as mistakes. The comparison is then exact. Each task contributes an accuracy score, and the final performance is the average over all selected tasks.

This method ensures consistency. Models cannot bluff with verbose text. They must produce the right short answer. That makes the results directly comparable, and it stresses the reasoning capabilities rather than the stylistic flourishes of the model.
-->

## Results

The baseline was the pretrained SmolLM2 without modification. It achieved an average accuracy of 22.5%, using 134M parameters. This experiment has a single measurement because no training was applied. The rest of the experiments was done using 3 random seeds.

When retrained with linear replacements, the model reached an average accuracy of 43.8%, with 46M trainable parameters (only last 5 blocks are active) and 5.87 GB VRAM total usage.

Replacing the last five feedforward blocks with Kolmogorov–Arnold Networks produced an average accuracy of 44.1%, with 39M parameters and 5.86 GB VRAM usage. The memory consumption of KAN layers is a subject that requires further optimization.

In short, KANs matched or slightly exceeded the reinitialized linear baseline in accuracy, while using fewer parameters and slightly less memory. This demonstrates that structured polynomial layers can substitute for large linear layers without degrading reasoning performance.

## Why Transfer Learning Works So Well

One of the surprising outcomes is how cleanly the pretrained Transformer integrates with KANs. Remember: only the feedforward modules in the last five blocks were replaced. All the other linear layers—embedding projections, attention queries, keys, and values, output heads—remained untouched. They continue to function as before. The new KAN blocks slot right in, adapt during training, and the system as a whole behaves coherently.

That tells us something important. The standard Transformer does not depend on linearity per se in those positions. What it depends on is a nonlinear transformation with enough expressive power. KANs provide that power, just in a different mathematical form. Which means: any pretrained Transformer can, in principle, be retrofit with KANs in the feedforward slots, no need to start from scratch.


## Looking Ahead: Mixing Polynomial Bases

So far we only tested one family, Chebyshev-2. But the architecture is more general. Each KAN block can in fact host multiple polynomial families in **parallel**, or stack them in **sequence**.

- **Parallel**: imagine splitting the input across several channels, each processed by a different basis. The outputs are then recombined. This way, one basis covers the smooth global structure, while another captures edge effects or oscillations.  
- **Sequential**: here, the output of one polynomial transformation becomes the input of another. You can think of it as layering function approximations, where the second basis corrects the limitations of the first. For example, a spline might give you piecewise smoothness, then a Chebyshev layer on top could adjust the global shape.

Both strategies were implemented and promise to extract more expressivity per parameter. Instead of simply making the networks bigger, we can make them *smarter*, combining the strengths of different mathematical families. That will be the focus of future work.


## Conclusion

The main lesson is this: language models do not need to be built entirely from massive linear matrices. By replacing just a handful of those matrices with compact Kolmogorov–Arnold modules, we achieved the same reasoning accuracy with fewer parameters and less memory. Transfer learning works cleanly. The architecture adapts. And the door is now open to rethink what belongs inside a Transformer block.

KANs are not just a theoretical curiosity. They are practical, efficient, and compatible with modern large language models. This project showed that replacing linear with polynomial is not only possible, it is competitive. The next step is to push combinations, explore scaling, and see just how far this mathematical alternative can take us.

<!--
## Bonus 1: Testing KANs as LoRA Replacement (Negative result)

We wanted to test if a degree-2 Chebyshev KAN could replace LoRA’s A and B or act as a nonlinear adapter and still match or beat LoRA at the same or smaller rank. In LoRA, A and B are the two small matrices that make the low-rank update: A maps input features down to a rank-r space, B maps that rank-r space back to output features, and their product BA is a constant ΔW that you add to the frozen weight and can merge at inference. We compared five variants at rank 2 and tracked best accuracy: standard LoRA on the final layer (lora_fc 32.03%), a mergeable KAN that generates A and B from Chebyshev bases over indices (11.69%), a linear low-rank conv adapter (81.86%), the same conv adapter with a SiLU in between (84.80%), and a KAN conv adapter (10.76%). The mergeable KAN lost to standard LoRA, and the KAN conv adapter lagged well behind both the linear and the SiLU controls. Conclusion: in this setup KAN did not deliver LoRA-level accuracy at smaller rank.

## Bonus 2 KAN Layers with LoRA for Domain Transfer (Negative result)

We tested if KANs (Cheby2, degree-2) adapt with LoRA as well as a plain linear MLP when moving from CIFAR-10 to CIFAR-100. We first trained both models on CIFAR-10, then froze them, added LoRA (rank 8) on the hidden layers and a new classifier, and matched the number of trainable parameters (~96k) for a fair test. Both models improved on CIFAR-100, but the linear MLP learned faster and reached higher accuracy (18.02% vs 23.10%). So, in this setup LoRA is less effective for KAN layers than for linear layers.
-->
