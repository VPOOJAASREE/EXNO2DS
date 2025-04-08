# EXNO2DS

NAME V. POOJAA SREE

REG. NO: 212223040147

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

## CODING AND OUTPUT:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df

```

# OUTPUT:
![1](https://github.com/user-attachments/assets/46bc374a-2fae-4b7f-bc13-931bb1245f76)

'''
df.info()

'''

# OUTPUT:
![2](https://github.com/user-attachments/assets/046a4f5d-8bae-4d67-b558-408b1e2e0f9e)


'''
df.shape

'''

# OUTPUT:
![3](https://github.com/user-attachments/assets/22decbc6-1134-46cf-8be5-0ca45e1f7da9)


'''
df.set_index("PassengerId",inplace=True)
df.describe()

'''

# OUTPUT:
![4](https://github.com/user-attachments/assets/186f3021-0814-4591-8bb7-21c6ab27aa6b)


'''
df.nunique()

'''

# OUTPUT:
![5](https://github.com/user-attachments/assets/fb863ed3-73b9-4457-ae3c-913bac5cef6a)


'''
df["Survived"].value_counts()

'''

# OUTPUT:
![6](https://github.com/user-attachments/assets/b1dd494e-b3a9-4b40-b6a8-2018497495ce)


'''
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per

'''

# OUTPUT:
![7](https://github.com/user-attachments/assets/aaa7e6d0-5554-49d0-aa20-53b500ecf620)


'''
sns.countplot(data=df,x="Survived")

'''

# OUTPUT:
![8n](https://github.com/user-attachments/assets/c05466b5-130b-4bc2-b298-10d10cc76702)


'''
df

'''

# OUTPUT:
![9](https://github.com/user-attachments/assets/2ed8bef1-29ca-4183-963e-610d8ac6aff9)


'''
df.Pclass.unique()

'''

# OUTPUT:
![10](https://github.com/user-attachments/assets/998d2f3a-d7c5-4925-a984-ed98852fafcd)


'''
df.rename(columns={'Sex':'Gender'},inplace=True)
df

'''

# OUTPUT:
![11](https://github.com/user-attachments/assets/a11f4951-603c-4529-a1b7-6903d6496126)


'''
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

'''

# OUTPUT:
![12 n](https://github.com/user-attachments/assets/a441a02a-e0ae-4532-89e6-7f1fe5b63426)


'''
sns.catplot(x='Survived',hue="Gender",data=df,kind='count')

'''

# OUTPUT:
![13](https://github.com/user-attachments/assets/01040e83-b71a-463f-9d5b-b791be6fc2d6)


'''
df.boxplot(column="Age",by="Survived")

'''

# OUTPUT:
![14](https://github.com/user-attachments/assets/a11b4186-c987-41dc-aeae-84847e82d03c)


'''
sns.scatterplot(x=df["Age"],y=df["Fare"])

'''

# OUTPUT:
![15](https://github.com/user-attachments/assets/d17be609-c258-45dc-8aba-d556f6328c7a)


'''
sns.jointplot(x="Age",y="Fare",data=df)

'''

# OUTPUT:
![16](https://github.com/user-attachments/assets/debba96a-d9df-4592-a628-771150e8664f)


'''
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=df)

'''

# OUTPUT:
![17](https://github.com/user-attachments/assets/5b554357-34d1-4fd3-bc4e-d94ada9a71b7)


'''
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")

'''

# OUTPUT:
![18](https://github.com/user-attachments/assets/d42e9bb5-5252-4c6c-930b-a3275d346610)


'''
numerical_df = df.select_dtypes(include=['number'])
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)

'''

# OUTPUT:
![19](https://github.com/user-attachments/assets/de36074a-cf86-4699-a12d-c4b2d8c8d7c2)


'''
sns.pairplot(df)

'''

# OUTPUT:
![20](https://github.com/user-attachments/assets/359bd293-cdb7-43c2-b3e6-3d109dfbc585)



# RESULT:

    Thus, the Exploratory Data Analysis on the given data set was performed successfully.
