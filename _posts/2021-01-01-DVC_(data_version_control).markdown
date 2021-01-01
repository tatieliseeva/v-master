---
layout: post
title:  "Data Version Control (DVC)"
categories: data_analysis, dataset
permalink: /discoveries/
---

Data Version Control (DVC) allows easily keeping track of changes to models or datasets. Its main feature is that it mimics git commands. DVC can be downloaded from dvc.org. The repository can be either on the same computer on in the cloud. For every model or dataversion will be generated a small text file. this file is lightweight and it can also be stored on git with corresponding code. 

## Install DVC and set up environment

To install DVC, one has to activate an environment an execute the following commands:


```python
$ python -m pip install dvc
```

After it, download your repository from GitHub:

```python
$ git clone https://github.com/YourUsername/data-version-control
$ cd data-version-control
```


