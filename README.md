# Frequently-used-code-ML
Frequently used code lines during various Machine Learning Projects. Can be helpful during interviews.


**One hot encoding**
```
from sklearn.preprocessing import OneHotEncoder

def encoding(encode_col_name,data_frame): 
    hot_encode = OneHotEncoder()
    hot_encode.fit(data_frame[encode_col_name]) # column can be one or more
    data_frame[list(hot_encode.get_feature_names_out())] = hot_encode.transform(data_frame[encode_col_name]).toarray()
    return data_frame 
```

**Concatinating Two Dataframes**
```
new_dataframe = pd.concat([dataframe_1,dataframe_2],axis=1) # axis = 1 to stack two dataframes vertically else 0.
```

**Removing Zero/Low variance features/columns from dataframe**
```
from sklearn.feature_selection import VarianceThreshold

var_thr = VarianceThreshold(threshold = 0.0) #Removing var<=0 columns
var_thr.fit(dataframe)
zero_variance_columns = dataframe.columns[~var_thr.get_support()]
new_dataframe = dataframe.drop(zero_variance_columns,axis=1)
```




