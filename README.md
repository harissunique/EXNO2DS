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
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![](./1.png)

df.head()
![](./2.png)

df.tail()
![](./3.png)

df.describe()
![](./4.png)

df.info()
![](./5.png)

df.shape
![](./6.png)

df.set_index("PassengerId",inplace=True)
df
![](./7.png)

df.nunique()
![](./8.png)

df["Survived"].value_counts()
![](./9.png)

per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
![](./10.png)

sns.countplot(data=df,x="Survived")
![](./11.png)

df.Pclass.unique()
![](./12.png)

df.rename(columns={'Sex':'Gender'},inplace=True)
df
![](./13.png)

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
![](./14.png)

sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
![](./15.png)

df.boxplot(column="Age",by="Survived")
![](./16.png)

sns.scatterplot(x=df["Age"],y=df["Fare"])
![](./17.png)

sns.jointplot(x="Age",y="Fare",data=df)
![](./18.png)

fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
![](./19.png)

sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
![](./20.png)

corr=df.corr()
sns.heatmap(corr,annot=True)
![](./21.png)

sns.pairplot(df)
![](./22.png)




# RESULT
        The EDA Analysis using python is executed successfully.
