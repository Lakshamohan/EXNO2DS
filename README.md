# NAME: LAKSHA.M
# REGNO: 212224220050
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
# OUTPUT
<img width="1567" height="689" alt="image" src="https://github.com/user-attachments/assets/05170cb7-72da-4bc1-a84f-ffa4a4f406d7" />

```
df.info()
```
# OUTPUT
<img width="700" height="478" alt="image" src="https://github.com/user-attachments/assets/a4e156f5-1de5-409c-b1ad-de92193e58c8" />

```
df.describe()
```
# OUTPUT
<img width="1033" height="415" alt="Screenshot 2025-09-23 111455" src="https://github.com/user-attachments/assets/d29dafdd-463a-4c41-92d0-95142bd9e4a8" />

```
df.dtypes
```
# OUTPUT
<img width="435" height="613" alt="image" src="https://github.com/user-attachments/assets/90e36b43-2043-4f99-bd15-854c79bf9634" />

```
df.shape
```
# OUTPUT
<img width="249" height="88" alt="image" src="https://github.com/user-attachments/assets/f7167bea-112e-490d-b98c-74aa9a2765d3" />

```
df.value_counts()
```
# OUTPUT
 <img width="1580" height="600" alt="image" src="https://github.com/user-attachments/assets/8df0f529-0cac-41df-810b-f6d2517299f8" />

```
df['Age'].value_counts()
```
# OUTPUT
<img width="436" height="651" alt="image" src="https://github.com/user-attachments/assets/de64bb5e-ef52-4285-8725-d2dcbea85684" />

```
df.set_index("PassengerId", inplace=True)
df
```
# OUTPUT
<img width="1526" height="627" alt="image" src="https://github.com/user-attachments/assets/d32a8d13-c24a-4d8e-92c3-47544fbcad16" />

```
df.nunique()
```
# OUTPUT
<img width="304" height="582" alt="image" src="https://github.com/user-attachments/assets/80072eb9-44bf-464b-aaff-1b5714688e81" />

```
sns.countplot(data=df,x='Survived')
```
# OUTPUT
<img width="924" height="614" alt="image" src="https://github.com/user-attachments/assets/d3a996d5-30af-4518-982d-013e7801fc06" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
# OUTPUT
<img width="1541" height="626" alt="image" src="https://github.com/user-attachments/assets/2d0520ca-016f-436f-a869-54d2ef3eb754" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
# OUTPUT
<img width="1167" height="691" alt="image" src="https://github.com/user-attachments/assets/63ced56f-6744-498c-a1be-fc22524bf60b" />

```
df.boxplot(column="Age",by="Survived")
```
# OUTPUT
<img width="927" height="663" alt="image" src="https://github.com/user-attachments/assets/bd71aa89-80f2-4531-92d1-44fefe97c196" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
# OUTPUT
<img width="889" height="621" alt="image" src="https://github.com/user-attachments/assets/6b65b0e8-e378-4bf0-b3e0-c411ba58c9b0" />

```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```
# OUTPUT
<img width="1028" height="640" alt="image" src="https://github.com/user-attachments/assets/bd0a5723-a519-4a53-806f-228f19329e48" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
# OUTPUT
<img width="891" height="608" alt="image" src="https://github.com/user-attachments/assets/ef009cd4-7121-4903-a054-7d505ab0ce99" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
# OUTPUT
<img width="1402" height="706" alt="image" src="https://github.com/user-attachments/assets/b8fd69c9-5b88-4f37-9a6a-019622002787" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```
# OUTPUT
<img width="1449" height="695" alt="image" src="https://github.com/user-attachments/assets/2ac91130-6a28-4910-84be-5578c2a98fa3" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
# OUTPUT
<img width="746" height="636" alt="image" src="https://github.com/user-attachments/assets/8e8f269e-cc9b-4bef-b17a-3a0ac8ab0e6e" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
# OUTPUT
<img width="814" height="626" alt="image" src="https://github.com/user-attachments/assets/382819e2-a235-4ffc-91b0-cf5db47b604a" />

# RESULT
Thus Exploratory Data Analysis is performed on the given data set
