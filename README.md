
### Name: Praveen.k
### RegNo:212223040152
# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output:
```
import numpy as np
import pandas as pd
data=pd.read_csv("/content/SAMPLEIDS.csv")
data
```

# Output:

<img width="1219" height="721" alt="image" src="https://github.com/user-attachments/assets/81494d48-ad79-4e27-8e50-0a6884df3f0e" />


```
data.head(4)

```
# Output:

<img width="1175" height="351" alt="image" src="https://github.com/user-attachments/assets/84cd3824-b139-4501-a459-36994734ce3c" />


```
data.tail(7)
```


# Output:
<img width="1180" height="400" alt="image" src="https://github.com/user-attachments/assets/4247e648-d99d-4eab-8142-9eaa676f7050" />



```
data.isnull()
```


# Output:
<img width="1044" height="650" alt="image" src="https://github.com/user-attachments/assets/ae116602-fd66-4e40-8b64-76a20071e139" />


```
data.notnull()
```



# Output:
<img width="1013" height="651" alt="image" src="https://github.com/user-attachments/assets/fdca0fe8-a644-4f3d-b175-cfb95b32d6f4" />




```
data.isnull().sum()

```


# Output:
<img width="483" height="638" alt="image" src="https://github.com/user-attachments/assets/c1248c12-5447-4fd9-9f28-293427fd65d3" />



```
data.isnull().any()
```


# Output:
<img width="625" height="623" alt="image" src="https://github.com/user-attachments/assets/89fe4392-7d88-495c-993c-1601343b3db4" />



```
data.dropna(axis=0)

```


# Output:
<img width="591" height="659" alt="image" src="https://github.com/user-attachments/assets/8c306579-8c1e-4fd0-abf3-231439947ab9" />



```
data.dropna(axis=1)
```



# Output:
<img width="1176" height="623" alt="image" src="https://github.com/user-attachments/assets/eb713b44-f494-4286-8de0-236962348407" />




```
data.fillna(0)
```



# Output:
<img width="1181" height="662" alt="image" src="https://github.com/user-attachments/assets/1b1a1f7a-2294-4e6d-bb89-8f222abf88f9" />



```
data.fillna(method="ffill")
```


# Output:
<img width="1150" height="658" alt="image" src="https://github.com/user-attachments/assets/a6230c0b-e07a-412d-aa9e-cfcacf22a52b" />



```
data.bfill()
```



# Output:
<img width="1169" height="641" alt="image" src="https://github.com/user-attachments/assets/e55cf63e-41b5-473b-a62e-fe5f710c674d" />



```

data.fillna({'REGNO':0,	'NAME':'PRAVEEN'})
```



# Output:
<img width="1158" height="647" alt="image" src="https://github.com/user-attachments/assets/e80cd7ea-5310-428a-84ba-72b2a18766dd" />



```
ir=pd.read_csv("/content/iris.csv")
ir
```



# Output:
<img width="973" height="611" alt="image" src="https://github.com/user-attachments/assets/887aa0bb-f717-4242-855e-beb5cd073d3c" />




```
ir.describe()

```



# Output:
<img width="849" height="444" alt="image" src="https://github.com/user-attachments/assets/58f082a3-11cf-403d-9fd9-91677a8038b5" />



```
import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)

```



# Output:
<img width="985" height="645" alt="image" src="https://github.com/user-attachments/assets/c88b1f67-54b8-442a-af50-ec61371b2cad" />




```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```



# Output:
<img width="738" height="185" alt="image" src="https://github.com/user-attachments/assets/a943172e-d0f9-4eab-a81e-2a5cd8a1c4da" />




```
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```




# Output:
<img width="871" height="353" alt="image" src="https://github.com/user-attachments/assets/1f1caa8a-81e7-4d26-b413-215e710f285e" />



```
rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid

```



# Output:
<img width="973" height="596" alt="image" src="https://github.com/user-attachments/assets/7a59f3c6-19b9-46a1-b9df-5ce3589c4b79" />



```
rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']

```


# Output:
<img width="929" height="654" alt="image" src="https://github.com/user-attachments/assets/5957615f-8840-4d78-a677-10711dc9f165" />



```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z
```



# Output:
<img width="883" height="668" alt="image" src="https://github.com/user-attachments/assets/82bcdaf3-c695-47db-8588-cfd3a8a7db28" />



# Result
     Thus the programs are executed successfully.
