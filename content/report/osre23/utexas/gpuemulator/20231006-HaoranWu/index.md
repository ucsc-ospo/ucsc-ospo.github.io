---
title: "GPU Emulator for Easy Reproducibility of DNN Training -- Final Blog Post"
subtitle: ""
summary: ""
authors: [haoranwu]
author_notes: ["Student at the University of Chicago"]
tags: ["osre23"]
categories: [SoR'23]
date: 2023-10-06
lastmod: 2023-10-06
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
## Introduction
For the second half of the project, I spent some time reproducing the figures and then focused on hacking the source code of PyTorch to distinguish the Inter-GPU Computation (1GPU vs. 2GPUs). 

#### Summarization
* Finished reproducing figure 3, 4, 5, 6 from [GPU Emulator for Easy Reproducibility of DNN Training](https://ospo.ucsc.edu/project/osre23/utexas/gpuemulator).
* Explored into inter-GPU computation in order to reproduce figure 9. 

#### Reporsitory of Reproducing Figures
I have placed the repository of the deliverable here: https://github.com/FarFlyField/OSRE_DELIVERABLE/tree/main
To use the repository, you can use any machine with just CPU, or you may check the results by renting GPU from Chameleon, comparing the result with the emulator's. 

The repository covers how to setup and understand the data produced from it. You will need to understand the spreadsheet and some of the graphing files. 

#### Study of Inter-GPU Computation

I have dissected the source code in PyTorch to identify the computation time differences between using 1 GPU and 2 GPUs (inter-GPUs computation time). The one most significant difference is managed throughout the forward process. Here are a few most significant features that make the computation time longer when using 2 GPUs:

* When using 1 GPU, PyTorch would put the images used to train the model onto the GPU in the main application once and for all. However, using 2 GPUs, PyTorch will transfer the images before running forward using a parallel function. The function contains two features:
  * It dissects the images into multiple sections and puts them onto the GPUs respectively. 
  * It copied the model we need to train into the # of GPUs and create threads to train the models parallelly on these separate GPUs. 
* These two steps create a major time difference for the computation time we have for training multiple GPUs and also make the transfer time for using 2 GPUs smaller because we are counting the transferring time of images toward computation time. 
* After finishing running forward, the parallel function will gather the outputs from the two GPUs and send the output to the first GPU. 

After gathering the output to the first GPU, the code will train the next batch and repeat the steps of transferring data, copying images, running parallel forwarding, and gathering the outputs once again. 

The second significant difference that I’m working on right now is when PyTorch runs backward functions, which are more or less similar to forward but not the same at all. I have located the function loss.backward() function in our application code as the only contributor to the time difference in computation time. Here are a few tasks I did after locating it: 
* Recorded the functions’ call stack when using 1 GPU and 2 GPUs. 
* Recorded the time spent in the functions in the call stack of the functions. 
* Identified the inconsistency when measuring data, repeated and verified until the consistency is reached.

I have finished the basic measuring and drafting out the call stack but I haven’t figured out the exact differences. Because most of the functions are done in C++, printing out the inputs to evaluate the functions will be slightly harder but doable. 

The data recorded and analyzed are placed here:
https://docs.google.com/spreadsheets/d/1vFj-UE3mjtsHIc5OesKX1sDvr6fpPwtPUMl0pM3V8SA/edit?usp=sharing 
Summarized doc:
https://docs.google.com/document/d/10XWNwCZ3kLzy4i6WgJ6KPsujEs2X1gzXblZtUoqMuJw/edit
