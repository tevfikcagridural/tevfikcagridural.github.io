---
title: Preprocess Effects On PCA
date: 2022-09-11
tags:
- machine learning
- PCA
- preprocess
- scaling
- normalize
layout: post
description: 'Understanding different preprocess effects on PCA'
author: Tevfik Çağrı Dural
---

I came up with [this](https://www.reddit.com/r/datascience/comments/x89x48/is_it_normal_that_more_than_90_of_the_pca/?utm_source=share&utm_medium=ios_app&utm_name=iossmf) post on reddit few days ago and it seemed like people separeted in to two about scaling/normalizing the data before applying PCA.

I was interested in the subject and found [this](https://stats.stackexchange.com/questions/69157/why-do-we-need-to-normalize-data-before-principal-component-analysis-pca)

In this post I'm going to examine this. Studied colab notebook file can be found in [here](../_notebooks/Prepocessing_effects_on_PCA.ipynb)

## What is PCA


## Understanding Scaling - Normlizing Methods


## No Preprocess
![explained_variance_no_preprocess](/images/preprocess_effects_on_pca/explained_variance_no_preprocess.png)

--

![covariance_matrix_no_preprocess](/images/preprocess_effects_on_pca/covariance_matrix_no_preprocess.png)

## Standard Scaling
![explained_variance_standard_scaling](/images/preprocess_effects_on_pca/explained_variance_standard_scaling.png)

![covariance_matrix_standard_scaling](/images/preprocess_effects_on_pca/covariance_matrix_standard_scaling.png)

But why?

## Min Max Scaling
![explained_variance_minmaxscale](/images/preprocess_effects_on_pca/explained_variance_minmaxscale.png)

![covariance_matrix_minmaxscale](/images/preprocess_effects_on_pca/covariance_matrix_minmaxscale.png)

## Normalizing
![explained_variance_normalized](/images/preprocess_effects_on_pca/explaine_variance_normalized.png)

![covariance_matrix_normalize](/images/preprocess_effects_on_pca/covariance_matrix_normalized.png)



## Conclusion