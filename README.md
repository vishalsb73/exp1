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
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd
df=pd.read_csv('titanic_dataset.csv')
df
```
<img width="1121" height="405" alt="Screenshot 2025-10-16 212819" src="https://github.com/user-attachments/assets/40b83d08-4c8c-45bf-99cc-82bdc79cf8c9" />

```
df.info()
```
<img width="407" height="374" alt="Screenshot 2025-10-16 212826" src="https://github.com/user-attachments/assets/e64a94a6-15a5-4f68-b147-7055fe0ede7e" />

```
df.head()
```
<img width="1124" height="208" alt="Screenshot 2025-10-16 212835" src="https://github.com/user-attachments/assets/faaf9c0a-7839-4163-a549-1e4b23356ad8" />

```
df.nunique()
```
<img width="209" height="277" alt="Screenshot 2025-10-16 212841" src="https://github.com/user-attachments/assets/f330f0ff-de1a-4f61-8d32-0fc85254efde" />

```
df["Survived"].value_counts()
```
<img width="291" height="86" alt="Screenshot 2025-10-16 212846" src="https://github.com/user-attachments/assets/f4f39249-2dcd-441f-9157-2586c134c03a" />

```
sns.countplot(data=df,x="Survived")
```
<img width="741" height="537" alt="Screenshot 2025-10-16 212854" src="https://github.com/user-attachments/assets/e43c3801-ad53-4451-9d59-adec1f6d1749" />

```
df.rename(columns={"Sex" : 'Gender'}, inplace=True)
df
```
<img width="1146" height="417" alt="Screenshot 2025-10-16 212902" src="https://github.com/user-attachments/assets/f0e274f5-eb42-4070-ad48-8cfc623c7419" />

```
sns.catplot(x="Gender",col="Survived",kind="count", data=df,height=5,aspect=.7)
```
<img width="876" height="603" alt="Screenshot 2025-10-16 212914" src="https://github.com/user-attachments/assets/6d73ce19-3ed6-4b73-a9be-984aef9e22e0" />

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
<img width="702" height="598" alt="Screenshot 2025-10-16 212923" src="https://github.com/user-attachments/assets/78def9e9-7472-4f4c-9d5a-240dc13705e7" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="677" height="567" alt="Screenshot 2025-10-16 212930" src="https://github.com/user-attachments/assets/cd4a27a2-19c9-49f2-a8df-7a7efe7f4f42" />

```
sns.scatterplot(x=df["Age"],y=df['Fare'])
```
<img width="709" height="536" alt="Screenshot 2025-10-16 212935" src="https://github.com/user-attachments/assets/ae5c20a3-5d45-43d2-969a-74563af50b4c" />

```
sns.jointplot(x="Age",y="Fare",data=df)
```
<img width="805" height="708" alt="Screenshot 2025-10-16 212943" src="https://github.com/user-attachments/assets/147fe3fd-f29c-4e83-ae9c-e3ef5bd4d529" />

```
fig,ax1=plt.subplots (figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass', y='Age', hue='Gender', data=df)
```
<img width="825" height="508" alt="Screenshot 2025-10-16 212949" src="https://github.com/user-attachments/assets/7cfd6756-602e-42a4-9262-8599463b5dd2" />

```
corr = df. select_dtypes (include=['number']). corr()
sns. heatmap(corr,annot=True)
```
<img width="740" height="596" alt="Screenshot 2025-10-16 212956" src="https://github.com/user-attachments/assets/134748ca-1091-4233-b505-8bcba1a1c108" />

```
sns.catplot(data=df, col="Survived", x="Gender", hue="Pclass",kind="count")
```
<img width="1120" height="566" alt="Screenshot 2025-10-16 213011" src="https://github.com/user-attachments/assets/d9f0f0b9-b8d5-41e2-8bcd-4db869dd60ac" />


# RESULT
To perform Exploratory Data Analysis on the given data set is succesfully completed.
