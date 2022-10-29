# WorkShop_3

### AIM
 
 To Perform feature generation on the given dataset 
### ALGORITHM 

STEP 1 Read the given Data 

STEP 2 :Clean the Data Set using Data Cleaning Process 

STEP 3 Apply feature generation techniques to all the feature of the data set

STEP 4 Save the data to the file

### PROGRAM 

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

df=pd.read_excel("/content/Workshop_feature Engg.csv.xlsx")

df.head()

![Screenshot (249)](https://user-images.githubusercontent.com/86832944/198815815-eaf8635a-2046-4dac-9878-cadf294b58a9.png)

df.info()

![Screenshot (250)](https://user-images.githubusercontent.com/86832944/198815827-5bd36f49-7837-409a-a05a-bb672d855065.png)

df.isnull().sum()

![Screenshot (251)](https://user-images.githubusercontent.com/86832944/198815849-2e4c3584-578a-4b82-bfae-90802455e246.png)

 labelEncoder present in scikitlearn library
 
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['fueltype'] = le.fit_transform(df['fueltype'])

sns.set(style ="darkgrid")

sns.countplot(df['fueltype'])

![Screenshot (252)](https://user-images.githubusercontent.com/86832944/198815907-2a7a7cda-079e-41d1-a8c4-1df5ca905538.png)

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['CarName']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['CarName'], axis=1)

df.head(10)

![Screenshot (253)](https://user-images.githubusercontent.com/86832944/198815915-4adf660a-fe70-4867-85b6-5d3e1de8be27.png)

df = pd.get_dummies(df, prefix=['aspiration'], columns=['aspiration'])

df.head(10)

![Screenshot (254)](https://user-images.githubusercontent.com/86832944/198815971-8a5e8226-fd06-4bdb-8f62-076d08406bc9.png)

df = pd.get_dummies(df, prefix=['doornumber'], columns=['doornumber'])

df.head(10)

![Screenshot (255)](https://user-images.githubusercontent.com/86832944/198815984-5b9871ff-b664-4e82-ac6f-2f8ad06f797e.png)

df = pd.get_dummies(df, prefix=['carbody'], columns=['carbody'])

df.head(10)

![Screenshot (256)](https://user-images.githubusercontent.com/86832944/198816003-188909e7-b9df-4f02-b9c6-240944be236e.png)

df = pd.get_dummies(df, prefix=['drivewheel'], columns=['drivewheel'])

df.head(10)

![Screenshot (257)](https://user-images.githubusercontent.com/86832944/198816026-f499f42c-f250-4d45-9760-6dba424c721a.png)

df = pd.get_dummies(df, prefix=['enginelocation'], columns=['enginelocation'])

df.head(10)

![Screenshot (258)](https://user-images.githubusercontent.com/86832944/198816038-431bfcb9-5028-4324-920d-77d5d17649ee.png)

df = pd.get_dummies(df, prefix=['enginetype'], columns=['enginetype'])

df.head(10)

![Screenshot (259)](https://user-images.githubusercontent.com/86832944/198816050-39ddc506-a4c1-4625-9272-b558c25e20fd.png)

df = pd.get_dummies(df, prefix=['cylindernumber'], columns=['cylindernumber'])

df.head(10)

![Screenshot (260)](https://user-images.githubusercontent.com/86832944/198816075-d412d223-6cc2-4b15-a966-7d6b81e759f2.png)

### RESULT
Thus, Feature Generation techniques are applied on the given dataset and executed successfully.

