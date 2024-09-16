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
import pandas as pd import numpy as np import matplotlib.pyplot as plt import seaborn as sns df=pd.read_csv('/content/titanic_dataset.csv') df
![Screenshot 2024-09-16 145520](https://github.com/user-attachments/assets/b7818440-d76d-4a3b-83c1-134eea274782)

df.info()
![Screenshot 2024-09-16 145540](https://github.com/user-attachments/assets/e951e627-72c9-475f-97f4-cdec97fd2e83)

df.shape
![Screenshot 2024-09-16 145607](https://github.com/user-attachments/assets/30566915-433e-492a-b643-ba26b058d54d)

df.head(4)
![Screenshot 2024-09-16 145719](https://github.com/user-attachments/assets/e7a998eb-83ed-4024-84f0-481ed09ba27b)

df.describe()
![Screenshot 2024-09-16 145737](https://github.com/user-attachments/assets/8f0c082d-74e3-4bc7-b3e5-340ceb1fb9f8)

df.set_index("PassengerId",inplace=True) df.describe()
![Screenshot 2024-09-16 145757](https://github.com/user-attachments/assets/60f226b2-3333-4ec7-95cc-868850101c64)

df.nunique()
![Screenshot 2024-09-16 145831](https://github.com/user-attachments/assets/00ac806c-ff1a-42f3-9e5b-a1596918c715)

per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) per
![Screenshot 2024-09-16 145905](https://github.com/user-attachments/assets/0cfdf4b5-0aa5-414d-b2f4-27c3fa1b4d5b)

sns.countplot(data=df,x="Survived")
![Screenshot 2024-09-16 145926](https://github.com/user-attachments/assets/d07ea676-88f5-4c04-b249-43b478081bad)

df
![Screenshot 2024-09-16 145947](https://github.com/user-attachments/assets/414ddca9-926d-41b5-ac33-b3ba34d13e52)

df.Pclass.unique()
![Screenshot 2024-09-16 150026](https://github.com/user-attachments/assets/3e9e24ae-339d-4590-bbe2-64143afef981)

df.rename(columns= {'Sex':'Gender'}, inplace=True) df
![Screenshot 2024-09-16 150121](https://github.com/user-attachments/assets/fff3518d-e774-4def-ad21-106bbbcb2dfb)

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
![Screenshot 2024-09-16 150147](https://github.com/user-attachments/assets/eaf2e25a-6b9e-4828-8ad0-8c499256f59e)

sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
![Screenshot 2024-09-16 150207](https://github.com/user-attachments/assets/5945a01a-167f-4bf1-a2c4-f3207fba736b)

df.boxplot(column="Age",by="Survived")
![Screenshot 2024-09-16 150226](https://github.com/user-attachments/assets/41add531-28da-49b2-a106-62067494f7b1)

sns.scatterplot(x=df["Age"],y=df["Fare"])
![Screenshot 2024-09-16 150249](https://github.com/user-attachments/assets/ed05996a-9a80-4016-9b98-17901a6a33f7)

sns.jointplot(x="Age",y="Fare",data=df)
![Screenshot 2024-09-16 150313](https://github.com/user-attachments/assets/c4abd886-ca53-4ae6-9146-50bf7da35b5e)

fig,ax1 = plt.subplots(figsize=(8,5)) pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
![Screenshot 2024-09-16 150334](https://github.com/user-attachments/assets/ca30a0f6-a83e-42cd-9f97-4734d0afca80)

sns.catplot(data=df,col = "Survived",x = "Gender",hue="Pclass",kind = "count")
![Screenshot 2024-09-16 150437](https://github.com/user-attachments/assets/7971f374-dfd9-48ad-9057-235835d1c344)

sns.pairplot(df)
![Screenshot 2024-09-16 150457](https://github.com/user-attachments/assets/127edc36-fdda-4797-95bf-f31a2f707f67)

# RESULT
        Exploratory Data Analysis on the given data set is Successfully Executed .
