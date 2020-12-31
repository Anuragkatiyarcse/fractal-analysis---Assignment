#Import libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from scipy.stats import norm

# Load Dataset 
dataset_path = r"https://drive.google.com/uc?export=download&id=1flc3xQQRt3qatXNGRsTfnV6BPYs0rhCu"

df = pd.read_csv(dataset_path)
df.shape  

output:- (912000, 4)

# print data
pd.set_option('display.max_columns',None)
pd.set_option('display.max_rows',None)
df.head(6)

#output

Time	Signal1	Signal2	Label
0	2017-08-14 11:37:49.791	33668.091913	0.856726	A
1	2017-08-14 11:37:49.801	32564.903040	0.856705	A
2	2017-08-14 11:37:49.811	31454.043305	0.856683	A
3	2017-08-14 11:37:49.821	30335.387166	0.856659	A
4	2017-08-14 11:37:49.831	29207.142938	0.856634	A
5	2017-08-14 11:37:49.841	28066.378446	0.856607	A


df.info() # information of data type

output:-
RangeIndex: 912000 entries, 0 to 911999
Data columns (total 4 columns):
 #   Column   Non-Null Count   Dtype  
---  ------   --------------   -----  
 0   Time     912000 non-null  object 
 1   Signal1  912000 non-null  float64
 2   Signal2  912000 non-null  float64
 3   Label    912000 non-null  object 
dtypes: float64(2), object(2)
memory usage: 27.8+ MB


df.isnull().sum()  # check missing data

output:-
Time       0
Signal1    0
Signal2    0
Label      0
dtype: int64

# create heatmap chart s for checking data is clear or not
plt.figure(figsize=(16,9))  # set size of figure
sns.heatmap(df.isnull())

output:- pic no. 1
 .........................................................
