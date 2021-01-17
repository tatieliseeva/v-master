---
layout: post
title:  "Overfitting vs. Underfitting"
categories: ML
permalink: /discoveries
---
## General Tipps
- check out several LR with step 0.001;
- dropout helps to remove generalisation noise from a model;
## Overfitting
Overfitting is when a model is too complicated to save data generate features and therefore saves also irrelevant noise. That cause exellent performance on training data but fails to handle a data which is not yet been seen.
## Underfitting
Underfitting is an undercapasity of a chosen model. Means that the model is not anymore able to reduce neither test or validation loss. Can also be caused by insufficient data. Continuously decreasing line of test loss shows the model underfitting
