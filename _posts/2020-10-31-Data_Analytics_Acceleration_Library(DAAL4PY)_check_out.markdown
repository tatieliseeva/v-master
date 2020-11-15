---
layout: post
title:  "Data Analytics Acceleration Library (daal4py)"
categories: data_analysis, regression, daal4py
permalink: /discoveries/
---

Daal4py is based on **Intel Data Analytics Acceleration Lybrary**. This technology allows to decrease learning time for classic sklearn methods due to several acceleration tricks, including matrix transformation, which are based on Intel DAAL.
Daal4py can be installed with `conda install -c intel daal4py`

Usage example of the library is demosntrated 


```python
from sklearn.datasets import load_diabetes
from sklearn.ensemble import RandomForestClassifier as rfc
import daal4py

from timer import timer

def get_best_clf(name, clf, params):
    start = timer()
    grid_clf = GridSearchCV(estimator=clf, param_grid=params, n_jobs=-1, cv=5)
    grid_clf.fit(X, y)
    end = timer()
    learning_time = end - start
    print(learning_time)

    return name, learning_time, grid_clf.best_estimator_

data = load_diabetes()
X = data.data
y = data.target

params_RF = {
    'n_estimators': [1, 3, 5, 7, 10],
    'max_depth': [3, 5, 7, 9, 11, 13, 15],
    'min_samples_leaf': [2, 4, 6, 8],
    'min_samples_split': [2, 4, 6, 8, 10]
}

learn_data_skl = []
name, lrn_time, model = get_best_clf("RF_sklearn", rfc(random_state = 42), params_RF)
learn_data_skl.append([name, model, lrn_time])

learn_data_daal = []
name, lrn_time, model = get_best_clf("RF_daal4py", daal4py.sklearn.ensemble.RandomForestClassifier(random_state = 42), params_RF)
learn_data_daal.append([name, model, lrn_time])
```
