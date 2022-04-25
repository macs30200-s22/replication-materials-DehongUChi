[![DOI](https://zenodo.org/badge/484103277.svg)](https://zenodo.org/badge/latestdoi/484103277)

Dehong Lu

Import the necessary packages using the following codes:

```
import pandas as pd
import numpy as np
from collections import Counter
import re
import seaborn as sns
import matplotlib.pyplot as plt


from sklearn.linear_model import LinearRegression, Ridge, Lasso
from sklearn.ensemble import RandomForestRegressor
from sklearn.neighbors import KNeighborsRegressor

from sklearn.model_selection import train_test_split, GridSearchCV

from sklearn.feature_selection import SelectKBest, f_regression
from sklearn import preprocessing

from sklearn.pipeline import make_pipeline
```

Read the csv file that contains top 11 google search terms related to the search term "jobs"
```
gt_jobs_data_top10 = pd.read_csv('gt_jobs_data_top10.csv')
```

Run the following code to split the data into training and test data:
```
X1 = gt_jobs_data_top10.drop(['Month', 'Unemployment_rate'], axis=1)
y1 = gt_jobs_data_top10['Unemployment_rate']
X1_train, X1_test, y1_train, y1_test = train_test_split(X1, y1, test_size = 0.3, random_state = 1)
```

Run the following code to find the optimal number of features to use in the model: 
```
model_rf_1 = make_pipeline(SelectKBest(f_regression), RandomForestRegressor())
parameters = {"selectkbest__k": range(1, 10)}
gs1 = GridSearchCV(model_rf_1,
                      param_grid = parameters,
                      cv = 5,                   # 5 k-fold Cross Valdation
                      scoring = 'r2',     
                      n_jobs = -1)
gs1.fit(X1_train, y1_train)

gs1.best_estimator_
```

Plug in the number we found previously to fit the model 
```
skb1 = SelectKBest(f_regression, k=9)
X1_new_train = skb1.fit_transform(X1_train, y1_train)
X1_new_test = skb1.transform(X1_test)

skb1.get_feature_names_out()
```
See how the model performs on the test data:
```
clf_rf1 = RandomForestRegressor()
clf_rf1.fit(X1_new_train, y1_train)
clf_rf1.score(X1_new_test, y1_test)
```
