---
layout: post
title:  "Data Analytics Acceleration Library (daal4py)"
categories: data_analysis, regression, daal4py
permalink: /discoveries/DAAL
---

Daal4py is based on **Intel Data Analytics Acceleration Lybrary**. This technology allows to decrease learning time for classic sklearn methods due to several acceleration tricks, including matrix transformation, which are based on Intel DAAL.
Daal4py can be installed with `conda install -c intel daal4py` . Add intel channel with `conda config --add channels intel`

Usage example of the library is demonsntrated on the following code:


```python
from sklearn.datasets import load_diabetes
from sklearn.model_selection import GridSearchCV
from daal4py.sklearn.ensemble.decision_forest import RandomForestRegressor
from time import time
data = load_diabetes()
X = data.data
y = data.target
params = {
    'n_estimators': [3, 5, 7],
    'max_depth': [7, 9, 11, 13, 15],
    'min_samples_leaf': [4, 6, 8],
    'min_samples_split': [2, 4, 6, 8]
}
# add compare to sklear if needed
start = time()
grid_clf = GridSearchCV(estimator=RandomForestRegressor(), param_grid=params, 
                        n_jobs=-1, cv=5)
grid_clf.fit(X, y)
end = time()
learning_time = end - start
print(["Simple sklearn", learning_time])
```


