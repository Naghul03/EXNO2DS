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
df=pd.read_csv("/content/titanic_dataset (2).csv")
df
```
![image](https://github.com/user-attachments/assets/f4446faf-2b4d-40f6-8e88-f97fae11bbd5)
```
df.info()
```
![image](https://github.com/user-attachments/assets/c7897d3d-7c85-464c-9736-a2bb53fa55ae)
```
df.set_index("PassengerId",inplace=True)
```
```
df
```
![image](https://github.com/user-attachments/assets/e93e4cb0-df09-4dae-adc2-1c6b8c03aca4)
```
df.shape()
```
![image](https://github.com/user-attachments/assets/3a7a2ae9-1b6c-403b-9b95-2a2af6f59d78)
```      
df.describe()
```
![image](https://github.com/user-attachments/assets/1af17046-5781-4e37-8d35-836aed2a9132)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/0c32beaa-9628-4b66-9ef2-a5893581928e)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/ef088b81-0179-4061-9b49-0a3ea7628fd3)
```
ko=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
ko
```
![image](https://github.com/user-attachments/assets/7334583b-449a-480a-9cb7-9159f6062223)
```
import seaborn as sns
sns.countplot(data=df,x="Survived",hue="Survived")
```
![image](https://github.com/user-attachments/assets/3b991f2a-c927-4c52-abdd-19d3aca3a463)
```
df
```
![image](https://github.com/user-attachments/assets/ac83e4c2-b3b7-4e56-a348-c26dcf6e3730)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/fcd0bd76-c5ca-4659-b394-7603ccea9de5)
```
df.rename(columns={"Sex":"Gender"},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/4c806e82-b745-4117-9ed2-d0622b4b9eb3)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7,hue="Gender")
```
![image](https://github.com/user-attachments/assets/c6e0abc5-d665-4cb9-b3b6-814f73961d2b)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/15cd9e40-2473-4153-8e6b-02529148f0e4)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/87e5c92b-5e90-468c-910e-c79922edb0ce)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/678ff25e-8b72-452f-9715-e2a921dd4d66)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/8cc47a8b-87a4-45e1-b167-9a22743de9eb)
```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/b8833a86-7d5e-4af3-8d09-96b6998d9138)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/01534d61-9301-48be-9be9-062271e61378)
```
corr=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/329c7c43-2db9-4189-ab79-1a711018bdc6)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/bd3607c0-0b19-4496-b5ef-f463a1442661)
![image](https://github.com/user-attachments/assets/3a774c2f-ab92-42c5-b149-95a1dfb245bf)

# RESULT
Thus,the exploratory data analysis has been performed on the given data set.
