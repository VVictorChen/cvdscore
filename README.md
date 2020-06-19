# CVHealthEva

The CVHealthEva is a python package that assists doctors to evaluate individual cardiovascular status. Users can use it to calculate the cardiovascular age, absolute risk score（ARS）and relative risk score (RRS) of individuals.


## Installation and the matters needing attention
 Dependency package	
```
python >=3.6
xgboost >=0.90
```
 Installation
```
pip install cvdscore
```
 Please make sure the features name is the same as the example file (See DEMO_TESTV2.csv in Example document).

## Example
```
from xgboost import XGBClassifier
import pickle
import scipy.stats as st
import pandas as pd
import numpy as np
from urllib.request import urlopen
import CVHealthEva
test = pd.read_table('https://raw.githubusercontent.com/VVictorChen/cvdscore/master/Example/DEMO_TESTV2.csv',sep=',',encoding='utf_8_sig')
testdata= test.drop(['result_after3year'],axis =1 ,inplace=False) 
test.head()
X = CVHealthEva.preprocess(testdata)
X.head()
cvd_age = CVHealthEva.cvdage(X)
cvd_score = CVHealthEva.main_cvdscore(X)
```











