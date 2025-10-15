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

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt = pd.read_csv("titanic_dataset.csv")
dt

<img><img width="1026" height="341" alt="image" src="https://github.com/user-attachments/assets/2ea5fe06-7e69-483a-9659-4ad3d4e16db0" />

dt.info()

<img><img width="690" height="532" alt="image" src="https://github.com/user-attachments/assets/3f2e59e6-2887-4ba7-92c3-fe4969201920" />

dt.shape

<img><img width="203" height="33" alt="image" src="https://github.com/user-attachments/assets/08a9dd70-4ecb-4a71-957d-e3efdb7bd018" />

dt.set_index("PassengerId",inplace=True)
dt.describe()

<img><img width="835" height="351" alt="image" src="https://github.com/user-attachments/assets/e168fc87-5511-4eab-9893-9e07793dec34" />

dt.nunique()

<img><img width="239" height="659" alt="image" src="https://github.com/user-attachments/assets/05ebe09f-c522-4612-86ff-4ef5ce2f0e3c" />

dt["Survived"].value_counts()

<img>
per=(dt['Survived'].value_counts()/dt.shape[0]*100).round(2)
per

<img><img width="283" height="249" alt="image" src="https://github.com/user-attachments/assets/483264a7-749e-49a7-9fba-52e1d838c14a" />

sns.countplot(data=dt,x="Survived")

<img><img width="822" height="606" alt="image" src="https://github.com/user-attachments/assets/6efd102d-59d9-48ca-8f52-72e4b4fd0e5f" />

dt.rename(columns={'Sex':'Gender'},inplace=True)
dt

<img><img width="964" height="323" alt="image" src="https://github.com/user-attachments/assets/76dd0aea-8277-4adc-ae07-c9051f98c1da" />


sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")

<img><img width="838" height="690" alt="image" src="https://github.com/user-attachments/assets/c000fd91-cbdb-4247-b258-df2445f3da55" />

dt.boxplot(column="Age",by="Survived")

<img><img width="826" height="680" alt="image" src="https://github.com/user-attachments/assets/3130271b-45c9-4d75-90f3-712b3b773de1" />


sns.jointplot(x="Age",y="Fare",data=dt)

<img><img width="676" height="682" alt="image" src="https://github.com/user-attachments/assets/c1a6f968-d21b-4ada-b346-8d1cd9c0bedd" />

sns.pairplot(dt)

<img><img width="1033" height="656" alt="image" src="https://github.com/user-attachments/assets/8e5ea996-d38e-4812-9d1d-2927750d803f" />


import numpy as np
numeric_df = dt.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr,annot=True)

<img><img width="606" height="507" alt="image" src="https://github.com/user-attachments/assets/2e2921fd-cc03-4c79-9822-37f37efa3a6a" />
```
# RESULT
        <<INCLUDE YOUR RESULT HERE>>
