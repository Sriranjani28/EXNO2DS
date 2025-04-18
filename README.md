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
import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

dt=pd.read_csv("/content/titanic_dataset (2).csv")

dt

dt.info()
<img width="717" alt="SS 01" src="https://github.com/user-attachments/assets/23f06eca-76d2-4489-ab6d-fb36b68e4a3a" />

dt.shape
<img width="298" alt="SS 02" src="https://github.com/user-attachments/assets/c5a40db9-e4ec-4784-a9fa-39936ad2595b" />

<img width="273" alt="SS 03" src="https://github.com/user-attachments/assets/cb79a2cb-936c-442c-85b1-6f71b6b275df" />


dt.set_index("PassengerId",inplace=True)


dt.describe()

<img width="401" alt="SS 04" src="https://github.com/user-attachments/assets/56e72715-54bd-4bc5-b9ab-ad8109f8cf22" />

dt.nunique()

<img width="141" alt="SS 05" src="https://github.com/user-attachments/assets/6a6980f5-b20e-435a-bcad-d0bd0d30d2b6" />

dt["Survived"].value_counts()

<img width="146" alt="SS 06" src="https://github.com/user-attachments/assets/6f2ffa17-7a6b-4c4f-98af-f1ec3888fafd" />

per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)

per

<img width="179" alt="SS 07" src="https://github.com/user-attachments/assets/0e437fbf-3b37-43b2-a7a0-26d76757d157" />

sns.countplot(data=dt,x="Survived")

<img width="438" alt="SS 08" src="https://github.com/user-attachments/assets/4e1b9dad-f309-42a8-8b2d-1a7f828ac8fa" />

dt

<img width="793" alt="SS 09" src="https://github.com/user-attachments/assets/e73ff9a7-c895-4bca-a03e-541fcab09e04" />

dt.Pclass.unique()

<img width="243" alt="SS 10" src="https://github.com/user-attachments/assets/be773019-5a47-46ac-9e0a-1b2ee61da8bc" />

dt.rename(columns={'Sex':'Gender'},inplace=True)

dt

<img width="782" alt="SS 11" src="https://github.com/user-attachments/assets/e11dffc1-8ee2-4d50-a045-8e73b76f7a9a" />

sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)

<img width="617" alt="SS 12" src="https://github.com/user-attachments/assets/b5da2108-0c0a-49b0-9942-3c892845c23b" />

sns.catplot(x='Survived',hue="Gender",data=dt,kind = "count")

<img width="421" alt="SS 13" src="https://github.com/user-attachments/assets/1312a7e5-708e-4796-aab4-8e6c8e08127c" />

dt.boxplot(column="Age",by="Survived")

<img width="406" alt="SS 14" src="https://github.com/user-attachments/assets/4a49ce95-3bda-4682-a347-84d72b090449" />

sns.scatterplot(x=dt["Age"],y=dt["Fare"])

<img width="481" alt="SS 15" src="https://github.com/user-attachments/assets/f9500153-5f70-474a-a9c5-f42551275fdb" />

sns.jointplot(x="Age",y="Fare",data=dt)

<img width="509" alt="SS 16" src="https://github.com/user-attachments/assets/ed081bbe-660f-40db-906e-c782a647fb6b" />

fig,ax1=plt.subplots(figsize=(8,5))

pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)

<img width="519" alt="SS 17" src="https://github.com/user-attachments/assets/310fb292-824b-4ca0-9145-5355cb0902e8" />

sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")

<img width="766" alt="SS 18" src="https://github.com/user-attachments/assets/8e2a9358-36ac-4c12-a06f-9fa5aa1225fd" />

sns.pairplot(dt)

<img width="482" alt="SS 19" src="https://github.com/user-attachments/assets/4249688e-b6d1-42ee-9851-76c976281cea" />

# RESULT
        Thus Exploratory Data Analysis is performed on the given data set.
