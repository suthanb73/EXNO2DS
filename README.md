# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt = pd.read_csv("titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/a73f5926-6e6b-42bd-8928-fff9176f8f14)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/7030b967-ea5c-43a5-88a4-b592b0971d8f)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/d372a63a-76f0-45b7-8308-0dd6935121c2)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/e46f8c91-2355-44ee-9a6c-333087942867)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/efe2df01-c52c-495c-8b13-a4f81d6e02f2)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/2b7cd8d9-f8e5-400f-b2d0-84c37aa4abf4)
```
per=(dt['Survived'].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/810abfae-79ab-4b24-b864-9711a0fb808c)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/5efe8568-398d-4017-945a-85ad08bcc2f9)
```
dt
```
![image](https://github.com/user-attachments/assets/cbfb5114-5af6-438e-9332-d4cdb24aeae8)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/933a11a4-8ed4-4c10-b718-89c7fa26b721)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/61b9cce7-aebc-4059-bfd0-4eea399fef29)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/0725d799-f0f9-4db4-abf4-4959e85e4473)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/9506bc29-3ad7-4bab-9224-0f191b3482cd)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/fbeb70b6-9849-4784-b20b-fccab6bd1d6a)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/04749f50-ee9a-4a0a-85e0-707e815599a6)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/bf58525b-4bb3-4a2d-a91e-d92f2bc74f32)
```
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/user-attachments/assets/f91ce478-5be9-41fa-805d-5eacc377cf7d)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/8c310d5b-4ffb-48a5-a54e-a8e96f9ae808)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/498eb266-a68d-4ea9-be68-4c2860701f1f)
```
import numpy as np
numeric_df = dt.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/ccbb5f42-66e5-47f9-ae56-cbfcf1e4961d)

# RESULT
Thus exploratory data analysis on the given data set has been executed successfully.

