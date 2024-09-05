---
title: "Understanding Data Leakage in Machine Learning: A Focus on TF-IDF"
authors: [KyrillosIshak]
tags: ["osre24", "reproducibility"]
categories: ["SummerofReproducibility24"]
date: 2024-08-23
lastmod: 2024-08-23
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

# Introduction

In machine learning, data leakage is a critical issue that can severely impact model performance. It occurs when information from outside the training dataset is improperly used to create the model, leading to overly optimistic performance during evaluation. One common source of leakage comes from how features, such as those extracted using **TF-IDF** (Term Frequency-Inverse Document Frequency), are handled. In this post, we'll explore how data leakage can happen during feature extraction with TF-IDF and how it affects model accuracy.

# What is TF-IDF?

TF-IDF is a method used to evaluate how important a word is in a document relative to a collection of documents. It consists of two components:

1. **Term Frequency (TF)**: Measures how frequently a term appears in a document.
2. **Inverse Document Frequency (IDF)**: Reduces the importance of terms that appear frequently across many documents.

Together, they provide a weighted value for each word, which reflects its importance.

# How Data Leakage Occurs with TF-IDF

Data leakage with TF-IDF happens when the inverse document frequency (IDF) is calculated using the entire dataset (including the test set) before splitting it into training and test sets. This means the model has access to information from the test set during training, leading to artificially inflated results. This is a subtle form of data leakage, as it often goes unnoticed.

For example, when calculating the TF-IDF score, if the word "banana" appears more frequently in the test set but is considered during training, the model downplays its significance. As a result, the model may fail to predict correctly when "banana" is important in the test data.

# Why Does This Matter?

If the test data is included when calculating the IDF, the model gains unintended insight into the test set's word distribution. In real-world scenarios, the test data is supposed to be unseen during training. By allowing the model to see this information, you're essentially reducing the uncertainty that the model should have about future data.

# Impact of Data Leakage on Model Performance

Let's consider two cases to understand the impact of data leakage in detail:

1. **When a word is rare in the training set but common in the test set**: The model will underestimate the importance of this word during training, leading to poor performance when the word is critical in test documents.
2. **When a word is common in the training set but rare in the test set**: The model will overemphasize the word during training, leading to poor predictions when the word doesn’t appear as often in unseen data.

# Conclusion

Avoiding data leakage is crucial for building robust machine learning models. In the case of TF-IDF, ensuring that feature extraction is done **only on the training set** and not on the entire dataset is key to preventing leakage. Properly addressing this issue leads to better generalization and more reliable models in real-world applications.
