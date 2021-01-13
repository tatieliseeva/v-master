---
layout: post
title:  "Data Version Control (DVC)"
categories: data_analysis, dataset
permalink: /discoveries/
---

Data Version Control (DVC) allows easily keeping track of changes to models or datasets. Its main feature is that it mimics git commands. The repository can be either on the same computer on in the cloud. For every model or dataversion will be generated a small text file. this file is lightweight and it can also be stored on git with corresponding code. 

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
To create .dvc folder, type in command line:

```python
$ dvc init
```
This folder contains configuration information. To set up remote (or not) storage:

```python
$ dvc remote add -d remote_storage path/to/your/dvc_remote
```

Preferable data structure for repository:

```
data-version-control/
|
├── data/
│   ├── prepared/
│   └── raw/
|        ├── train/
|        ├── val/
|        └── test/
|
├── metrics/
├── model/
└── src/
    ├── evaluate.py
    ├── prepare.py
    └── train.py
```

## The first experiment:

```python
$ git checkout -b "first_experiment"
$ dvc init
```
And after to create a remote storage as described above. 

To initiate file tracing:
```$ dvc add data/raw/train
$ dvc add data/raw/val
```
Manage files: ```$ git add --all```

Commit on GitHub: ```$ git commit -m "start"```

To load files from cash to remote storage: ```$ dvc push```. DVC has also command ```commit```, but it is used in case if data was changed.

And, finally, add everything on GitHub: ```$ git push --set-upstream origin first_experiment```. Use ```--set-upstream``` only with the first push.
