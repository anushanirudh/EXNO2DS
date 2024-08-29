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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2024-08-29 105846](https://github.com/user-attachments/assets/3d776eb6-99af-4664-a2ac-aea22d0e878e)

```
df.info()
```
![Screenshot 2024-08-29 105934](https://github.com/user-attachments/assets/f505ed48-2380-428a-94ad-5b2010e016d9)

```
df.shape
```
![Screenshot 2024-08-29 110004](https://github.com/user-attachments/assets/166a8c33-05a8-4862-a9c9-10617720cbe8)

```
df.describe()
```
![Screenshot 2024-08-29 110032](https://github.com/user-attachments/assets/c1c506a8-f06f-4ca5-b80b-e2af9a3fe332)


```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2024-08-29 110137](https://github.com/user-attachments/assets/0517b624-bd02-43a2-80b5-026aa5450752)

```
df.nunique()
```
![Screenshot 2024-08-29 110204](https://github.com/user-attachments/assets/3f693753-2700-4f4f-bb01-3f700ffcf7ba)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) 
per
```

![Screenshot 2024-08-29 110233](https://github.com/user-attachments/assets/312294f1-535c-4b8a-87a0-6cfdb04ba186)

```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2024-08-29 110328](https://github.com/user-attachments/assets/f2bc3c9f-5251-44c6-86be-bb6baaa09d60)

```
df.Pclass.unique()
```
![Screenshot 2024-08-29 110354](https://github.com/user-attachments/assets/130d7431-70d4-498b-ae15-323f7ccc50a5)

```
df.rename(columns= {'Sex':'Gender'}, inplace=True)
df
```
![Screenshot 2024-08-29 110440](https://github.com/user-attachments/assets/30d17017-1071-40aa-afb7-bf61149d6e5a)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2024-08-29 110510](https://github.com/user-attachments/assets/890579ae-8e83-4fe5-934a-e1795b5d4fc2)

```
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```
![Screenshot 2024-08-29 110607](https://github.com/user-attachments/assets/f607704b-6905-4ade-9159-2603f9b7ac48)

```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-08-29 110634](https://github.com/user-attachments/assets/f2846ba5-f4a2-4c8b-9ac0-553200e24849)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2024-08-29 110701](https://github.com/user-attachments/assets/9456bafb-1b45-4ac0-8bf8-6e42b724d178)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2024-08-29 110741](https://github.com/user-attachments/assets/c7525f87-a20a-429a-8777-9131622cfcb5)

```
fig,ax1 = plt.subplots(figsize=(8,5)) 
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2024-08-29 110815](https://github.com/user-attachments/assets/7dce2f36-15b0-4778-8109-111ec987121b)

```
sns.pairplot(df)
```
![Screenshot 2024-08-29 110847](https://github.com/user-attachments/assets/b2922399-9f41-450d-ab1c-352e96b88c24)


# RESULT
Hence performing Exploratory Data Analysis on the given data set is successful
