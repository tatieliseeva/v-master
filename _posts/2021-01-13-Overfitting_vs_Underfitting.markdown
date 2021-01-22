---
layout: post
title:  "Overfitting vs. Underfitting"
categories: ML
permalink: /discoveries
---
## Training Tipps
- check out several LR with step 0.001, increasing the LR moves the training from underfitting towards overfitting;
- dropout helps to remove generalisation noise from a model;
- higher batch size decrease the time of convergention, but in general the size of a batch insignifically influence the model's accuracy, but can demonstrate slightly worse loss;
- LR is the most important hyperparameter of set LR, momentum, batch size and weight decay;
- momentum should be chosen as large as possible without causing the nets instabilities;
- if you have no idea of a reasonable value for weight decay, test 10−3 , 10−4 , 10−5 , and 0;
- bigger model - higher LR, and higher WD
## Overfitting
Overfitting is when a model is too complicated to save data generate features and therefore saves also irrelevant noise. That cause exellent performance on training data but fails to handle a data which is not yet been seen.
## Underfitting
Underfitting is an undercapasity of a chosen model. Means that the model is not anymore able to reduce neither test or validation loss. Can also be caused by insufficient data. Continuously decreasing line of test loss shows the model underfitting
## General
- Leaky ReLU always outperformes ReLU (+He initialization), ELU outperforms LReLU


Ref.:
[1] A DISCIPLINED APPROACH TO NEURAL NETWORK HYPER-PARAMETERS: PART 1 – LEARNING RATE, BATCH SIZE, MOMENTUM, AND WEIGHT DECAY https://arxiv.org/pdf/1803.09820.pdf
[2] Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow by Aurélien Géron
