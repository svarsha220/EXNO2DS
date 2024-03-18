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
NAME : ALdrin Lijo J E
Reg No : 212222240007
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic.csv")
dt
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/e7f6baa8-25fb-436d-ad48-1ece0f7f875b)

```
dt.info()
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/b6f38571-617d-443f-8917-c136b573e761)

```
dt.set_index('PassengerId',inplace=True)
dt.describe()
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/92c61908-b981-43d1-a0b1-0cdef3cbd068)

```
dt.shape
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/e848a8b1-f4fd-42b9-9d52-9509c1b7dc18)

```
dt.nunique()
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/1b88a1ee-9dd5-440a-985b-d4b662007d3e)

```
dt["Survived"].value_counts()
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/08e4cfab-b1ca-47ad-892c-35e92ce227c8)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/9b969225-4ee6-441f-866b-609f55575453)

```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/91d1e161-35bd-4d3a-94c6-7ba0722f6e36)

```
dt.Pclass.unique()
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/b5ef55c7-b8c6-41a2-a9be-a613ed29f62b)

```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/ddb5d4fc-e6d2-4493-94a9-b3c75fb97ebb)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/1f52ca0e-ce85-4584-a512-1f19a0fe7fac)

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/48fb7b93-5052-459c-bc17-7062d1cf1789)

```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/40057dd0-91b6-4eb9-bf9c-b03eed1b1877)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/8acc8865-04fc-48ac-9535-8674f4e3911c)

```
sns.jointplot(x=dt["Age"],y=dt["Fare"],data=dt)
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/3cf86d55-357c-4ea5-bc5a-bc7b909daccf)

```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/2f2d7d3b-29c1-45ee-b4dc-32d8247690f3)

```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/e338c010-89db-4781-845d-3001ad0288de)

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/ac44a5c9-8eb0-434d-b7f8-61ec2b3c644a)

```
sns.pairplot(dt)
```
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/d46f30d0-259c-42a9-9588-b990f6ff2342)
![image](https://github.com/svarsha220/EXNO2DS/assets/127709117/51379ed9-83fe-4fdc-ba89-1099e03bc5eb)


# RESULT
Thus,Data Analyzing of the given dataset was successful.
