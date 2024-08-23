---
title: "Data leakage in applied ML: reproducing examples of irreproducibility"
subtitle: "Exploring Data Leakage in Machine Learning Education" 
authors: [KyrillosIshak]
tags: ["osre24", "reproducibility"]
categories: ["SummerofReproducibility24"]
date: 2024-06-14
lastmod: 2024-06-14
draft: false
featured: false

# Featured image

# To use, add an image named `featured.jpg/png` to your page's folder.

# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.

image:
caption: ""
focal_point: "TopLeft"
preview_only: false
---

Hello!

I was exploring and reproducing : 

> Benedetti, P., Perri, D., Simonetti, M., Gervasi, O., Reali, G., Femminella, M. (2020). Skin Cancer Classification Using Inception Network and Transfer Learning. In: Gervasi, O., et al. Computational Science and Its Applications – ICCSA 2020. ICCSA 2020. Lecture Notes in Computer Science(), vol 12249. Springer, Cham. https://doi.org/10.1007/978-3-030-58799-4_39 [arXiv](https://arxiv.org/pdf/2111.02402v1)

In this paper, the authors use transfer learning on a pretrained convolutional neural network to classify skin lesions in dermatoscopic images from HAM10000 (Human Against Machine with 10000 training images) dataset. The paper reports a final accuracy of 78.9% on the validation set.

Their result achieves approximately 78.87% accuracy on the validation set, However, although this seems like a good result, we do not expect the model to achieve such a high accuracy when used to classify new lesions. The original result was trained and evaluated with *data leakage* - where there is contamination between the training set and validation or test set, in a way that will not be present when the model is used in production. Specifically, this example has a kind of data leakage where there are duplicate images of the same lesion in both the training set and the validation set that is used to evaluate model performance. This leads to an *overly optimistic evaluation* on the validation set - we were validating the model using an "easier" task than we had intended: classify lesions already seen in traning.

![Lesions](leakage.png)

Also there is another data leakage problem in the original: using the validation set for both early stopping and for evaluation of model performance. We will see that the final accuracy is lower when the model is evaluated correctly.

<table>
  <tr>
    <td></td>
    <td>Original results</td>
    <td>Our results</td>
  </tr>
  <tr>
    <td>
        Accuracy
    </td>
    <td>
        78.9%
   </td>
    <td>
        78.6%
    </td>
  </tr> 
  <tr>
    <td>
        Number of epochs
    </td>
    <td>
        Approx. 42 epochs
    </td>
    <td>
        40 epochs
    </td>
  </tr>
  <tr>
    <td>
        Training size
    </td>
    <td>
        Unknown
    </td>
    <td>
        7000 samples
    </td>
  </tr>
  <tr>
    <td>
        Validation size
    </td>
    <td>
        478 samples
    </td>
    <td>
        478 samples
    </td>
  </tr>
  <tr>
    <td>
        Confusion martix
    </td>
    <td>
      <img src="https://raw.githubusercontent.com/kyrillosishak/re-SkinCancer/main/assets/paper's_results.jpeg" />
    </td>
    <td>
        <img src="https://raw.githubusercontent.com/kyrillosishak/re-SkinCancer/main/assets/Our_results.jpeg" />
    </td>
  </tr>
  
</table>
