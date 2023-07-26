---
title: "Halfway Through GSOC: My Experience and Learnings"
subtitle: "Using Reproducibility in Machine Learning Education"
summary: ""
authors: [kokoedwin]
tags: ["osre23", "reproducibility"]
categories: ["SummerofReproducibility23"]
date: 2023-07-17
lastmod: 2023-07-26
featured: false
draft: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false
---

Hello there! I'm Jonathan Edwin, all the way from the beautiful archipelago of Indonesia. This year, I got the exciting chance to jump on board the 2023 Summer of Reproducibility initiative. It's been quite the adventure! Right now, I'm pouring my energy into a fascinating project titled [Using Reproducibility in Machine Learning Education](/project/osre23/nyu/eduml) project. I'm thrilled to be able to make my own little mark on it.

For those of you who are not familiar with what I'm working on, let me shed some light. My project, as part of the "Using Reproducibility in Machine Learning Education" initiative under guidance of {{% mention ffund %}}, focuses on creating educational resources that center around reproducing some key machine learning techniques. These include Cutout data augmentation, U-Net, and Siamese networks, to name a few. The end product will be a series of interactive Jupyter notebooks that provide step-by-step guidance for students, helping them not only understand these complex models but also gain hands-on experience in achieving research reproducibility. 

**Progress and Challenges**

Embarking on this project, I dove headfirst into the world of Cutout data augmentation, immersing myself in the many experiments outlined in the foundational paper. This initial study proved to be an intricate blend of multiple datasets, two network architectures, and a performance evaluation of models with and without Cutout data augmentation. Additionally, it included the exploration of these models in combination with other data augmentation techniques.

One of our main objectives has been to help students visualize how the model interacts with the data, and for this, we've been leveraging a tool called Grad-CAM. The initial paper provided a rich landscape for exploration and learning, leading us to segment our journey into six interactive Jupyter notebooks - Introduction, CutOut, ResNet, WideResNet, Shake-Shake Regularization, and Grad-CAM.

I'm excited to share that, as we've hit the mid-term milestone, I've managed to make significant strides and completed the notebooks up to the WideResNet section. It's been a journey full of learning and growth, overcoming various challenges along the way - understanding the intricacies of the experiments, deconstructing complex architectures, and distilling all this into digestible, interactive notebooks for students. Despite the challenges, the process has been incredibly rewarding. As we gear up for the next half of the project, I'm eager to tackle the remaining sections and share my work with the community.

**Learnings and Skills Gained**

***Embracing the Iterative Process of Open Source Development***: My initial foray into open source development had me writing code independently before pushing it to GitHub. This occasionally led to mistakes during the code migration. However, I've since learned that it's perfectly acceptable to push unfinished code, run it, catch errors, and improve. In open source development, the end goal is to ensure everything works flawlessly, even if it involves several iterations. This is especially true considering the code from GitHub might directly run on platforms like Chameleon or Google Colab.

***Understanding the Distinction between Reproducing Experiments and Crafting Educational Content***: There's a stark difference between merely reproducing an experiment from a research paper and creating an educational resource around that experiment. The former generally involves cloning and running the code, verifying it against the claims in the paper with minimal modifications. The latter, however, necessitates adapting and simplifying the code, regardless of the learner's skill level, to ensure their comprehension. It's about carefully guiding learners through each step for a more profound understanding.

***The Power of 'Show, Don’t Tell'***: This priceless lesson was imparted by my mentor, Ms. Fraida Fund. Rather than telling me what to do when I erred or needed to learn something new, she demonstrated the correct way first-hand. This hands-on approach made understanding far easier. This principle is also reflected in the creation of our notebooks. For instance, we chose to include the Grad-CAM notebook. Although not directly referenced in the paper, it offers students a clear visual understanding of the impact of the Cutout technique, embodying the "show, don’t tell" philosophy.

**Next Steps**

As we step into the second half of this thrilling journey, our primary goal is to complete the remaining sections of our Cutout project. We're setting our sights on the final two notebooks - Shake-Shake and Grad-CAM. The Shake-Shake notebook will delve into the nuances of Shake-Shake regularization, an exciting topic with vast implications. Meanwhile, the Grad-CAM notebook will offer a visual exploration of how our models interpret and interact with data, thereby solidifying the students' understanding of Cutout data augmentation. So, stay tuned for more as we plunge into these fascinating topics!

**Conclusion**

Looking back, my time with the Summer of Reproducibility initiative has been nothing short of a profound learning experience. Working on the "Using Reproducibility in Machine Learning Education" project has been both challenging and rewarding, and I am incredibly grateful for this opportunity.

I've gained valuable insights into open-source development, delved deeper into the intricacies of machine learning techniques, and experienced firsthand the transformative power of a 'show, don't tell' teaching approach. Moreover, I've learned that the creation of educational resources requires a delicate balance between preserving the essence of original research and adapting it to foster easy understanding.

As we press forward, I'm excited about the prospects of the coming weeks. The completion of the Shake-Shake and Grad-CAM notebooks lies ahead, marking the final pieces of our Cutout project. Beyond this project, the skills and lessons I've acquired during this initiative will undoubtedly guide me in future endeavours.

I can confidently say that my GSOC journey has been a remarkable chapter in my growth as a developer and researcher. Here's to more learning, more coding, and more breakthroughs in the future!








