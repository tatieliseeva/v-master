---
layout: post
title:  "Data Analytics Acceleration Library (daal4py)"
categories: data_analysis, regression, daal4py
permalink: /discoveries/
---

Daal4py is based on **Intel Data Analytics Acceleration Lybrary**. This technology allows to decrease learning time for classic sklearn methods due to several acceleration tricks, including matrix transformation, which are based on Intel DAAL.

{% highlight python %}
    from sklearn.datasets import load_diabetes
    from sklearn.model_selection import GridSearchCV
    data = load_diabetes()
    X = data.data
    y = data.target
{% endhighlight %}


```python
# Here is some in python
from sklearn.datasets import load_diabetes
from sklearn.model_selection import GridSearchCV
data = load_diabetes()
X = data.data
y = data.target
```


```python
# Here is some in python
def foo():
  print 'foo'
  
X = data.data
```


