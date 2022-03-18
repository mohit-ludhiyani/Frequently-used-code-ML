# Frequently-used-code-ML
Frequently used code lines during various Machine Learning Projects. Can be helpful during interviews.


**One hot encoding**
```
def encoding(encode_col_name,data_frame): 
    hot_encode = OneHotEncoder()
    hot_encode.fit(data_frame[encode_col_name]) # column can be one or more
    data_frame[list(hot_encode.get_feature_names_out())] = hot_encode.transform(data_frame[encode_col_name]).toarray()
    return data_frame 
```
