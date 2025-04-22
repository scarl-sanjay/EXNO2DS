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

dt=pd.read_csv("/content/titanic_dataset (2).csv")
dt
```
![image](https://github.com/user-attachments/assets/87650cc5-74bd-466b-9f27-72fdbe38a893)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/00581025-f3b5-4f3d-9db0-5d08a19fd8bd)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/cfc02bc2-6494-4662-8bdc-4cabd4aaec40)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![image](https://github.com/user-attachments/assets/ecc32632-cb91-47ba-b154-f96c77a8bbd4)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/bf4d4a59-0064-495d-bd24-952f362f943a)
```
dt.nunique()
```
![image](https://github.com/user-attachments/assets/c38e9d38-0c2b-4b8f-956c-95e7ed2e1dad)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/0e3fd43e-6994-4281-a252-cc48c18bed48)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/b55d57b1-6de3-4f3f-8e87-39bebc80b7f4)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/4413303c-4567-4fa3-ad2f-b147522a2bf1)
```
dt
```
![image](https://github.com/user-attachments/assets/687749ba-8f5c-4d40-b82b-f71bffef749d)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/cf580168-1067-4065-9d45-b33e87f7fd09)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/8b8b38b0-9919-4528-b9f7-86da1531e298)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/fad433b5-78dc-4972-a25f-28012d89c109)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/4ef50dcf-1c79-4ac0-b77c-1f6496446573)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/fd19ca27-9730-4998-9d63-88930877b8f7)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/432f2595-a34c-46d7-8f9d-f9a62ab0a023)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/65882e48-8dba-4fa0-b5fc-3d75d0c53832)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/user-attachments/assets/912ad44e-eea3-45b0-ad90-eaf195fa2adc)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/544bd6d6-2ab5-4764-becd-ecde8cfafc5a)
```
numeric_dt=dt.select_dtypes(include=['int64','float64'])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/64e2ce1b-b38b-4d2b-9d69-43302b170f51)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/35153081-c39f-4996-8427-bdf68b88ce75)

# RESULT
         Exploratory Data Analysis on the given data set was performed successsfully.
