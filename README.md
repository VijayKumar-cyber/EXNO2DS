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
<img width="1446" height="625" alt="Screenshot 2025-09-15 114123" src="https://github.com/user-attachments/assets/8975a1f2-ee14-4614-b0fb-d28115302bb2" />

```
df.info()
```

<img width="583" height="433" alt="Screenshot 2025-09-15 114157" src="https://github.com/user-attachments/assets/c977ee27-2c5a-4bfb-ae9f-9263cb8057c2" />

```
df.describe()
```

<img width="934" height="374" alt="Screenshot 2025-09-15 114216" src="https://github.com/user-attachments/assets/e42df259-e8e2-4481-85ae-0ddcdb2a9eae" />

```
df.dtypes
```

<img width="338" height="572" alt="Screenshot 2025-09-15 114228" src="https://github.com/user-attachments/assets/1bdd977d-37e7-44af-9976-3260a284e9f6" />

```
df.shape
```

<img width="255" height="67" alt="Screenshot 2025-09-15 114240" src="https://github.com/user-attachments/assets/45ae4e1a-17d5-4f2c-b410-bf0e2040eeb4" />

```
df.value_counts()
```

<img width="1405" height="692" alt="Screenshot 2025-09-15 114317" src="https://github.com/user-attachments/assets/2009979d-fb60-4a6a-b3ee-ede84dd06d93" />

```
df['Age'].value_counts()
```

<img width="326" height="617" alt="Screenshot 2025-09-15 114330" src="https://github.com/user-attachments/assets/3090df36-2f0b-431a-aeb6-dc5c9a27b50b" />

```
df.set_index("PassengerId",inplace=True)
df
```
<img width="1359" height="643" alt="Screenshot 2025-09-15 114349" src="https://github.com/user-attachments/assets/6db6d979-3354-4cc9-aee8-62d5aa01437b" />

```
df.nunique()
```
<img width="271" height="532" alt="Screenshot 2025-09-15 114402" src="https://github.com/user-attachments/assets/4add6996-3a28-46a8-918c-4f1495cf23a8" />

```
sns.countplot(data=df,x="Survived")
```
<img width="848" height="593" alt="Screenshot 2025-09-15 114418" src="https://github.com/user-attachments/assets/e490e6cb-e516-4c3d-bd81-74e71f768a8c" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1367" height="656" alt="Screenshot 2025-09-15 114435" src="https://github.com/user-attachments/assets/f9ea661b-7091-4c55-91b4-b6d7e6ec78b8" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="1028" height="654" alt="Screenshot 2025-09-15 114449" src="https://github.com/user-attachments/assets/acfb18b6-5f7a-4458-ab6f-0e45dcf13b7c" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="805" height="627" alt="Screenshot 2025-09-15 114504" src="https://github.com/user-attachments/assets/a370b598-09f7-47e1-8b0f-ad4d9a09b718" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="872" height="586" alt="Screenshot 2025-09-15 114523" src="https://github.com/user-attachments/assets/c36778ff-d66b-4276-b4ec-ed46ba31442b" />

```
flg, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="1026" height="583" alt="Screenshot 2025-09-15 114540" src="https://github.com/user-attachments/assets/0818de80-e14f-42be-bd17-f69c764431a6" />

```
import seaborn as sns
sns.catplot(x="Pclass",y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="1391" height="642" alt="Screenshot 2025-09-15 114556" src="https://github.com/user-attachments/assets/dca834f5-cbcc-4b8a-9b2c-3897312811b9" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="748" height="563" alt="Screenshot 2025-09-15 114610" src="https://github.com/user-attachments/assets/e5383a62-3681-4141-9f7b-f8f4f05e96d6" />


# RESULT

Thus exploratory data analysis on the given data set has been executed successfully. 
        
