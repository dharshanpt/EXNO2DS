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
NAME: S KAVIYA
REGISTRATION NO. : 212223040090
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
![image](https://github.com/user-attachments/assets/3112e5e3-eb81-4dc9-b1fe-1a8b308dd29c)

```
df.info()
```

![image](https://github.com/user-attachments/assets/97e926b5-ed51-433d-a0c0-28dc55cf9bc5)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```

![image](https://github.com/user-attachments/assets/2b21de6b-a3e4-47be-9c61-4d8de7e7ffa8)

```
df.nunique()
```

![image](https://github.com/user-attachments/assets/25de61d4-f5d0-4d2a-8383-fa93a86112f8)

```
df["Survived"].value_counts()
```

![image](https://github.com/user-attachments/assets/403fade7-56b7-4111-b92b-a25eb12efb5a)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

![image](https://github.com/user-attachments/assets/00156f9a-55b3-4b56-a90c-d773c98afae0)

```
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/user-attachments/assets/df48820a-94f2-4bd3-a219-b59a6fb1c246)

```
df
```

![image](https://github.com/user-attachments/assets/54d48094-6302-4706-96d4-80b81283c209)

```
df.Pclass.unique()
```

![image](https://github.com/user-attachments/assets/b1d58823-ea16-4511-8b67-793fb714b5d1)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

![image](https://github.com/user-attachments/assets/ca843988-d783-4eea-a4db-ead38d78472c)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

![image](https://github.com/user-attachments/assets/2bcec3f3-d7ea-4e6b-8c4b-2659e59911b8)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

![image](https://github.com/user-attachments/assets/a62b50da-21c0-4477-9085-0467ebe904b4)

```
df.boxplot(column="Age",by="Survived")
```

![image](https://github.com/user-attachments/assets/4641f2e8-d347-4e27-af1e-bea879b52623)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

![image](https://github.com/user-attachments/assets/a58244ba-93e9-4b82-ab8e-673012991e07)

```
sns.jointplot(x="Age",y="Fare",data=df)
```

![image](https://github.com/user-attachments/assets/f744fd36-4327-461a-a901-38bdf504ac74)

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

![image](https://github.com/user-attachments/assets/6eda8092-6ba1-4b56-b822-165ff9ce7278)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/8891456e-1a83-4d5d-9f8e-f02192517823)

```
corr=df.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/user-attachments/assets/4fd1758f-662c-4f68-aa2d-3b1ea76a22e9)

```
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/95b6e9e7-9022-414e-b892-ebbe68461c28)


## RESULT:
Thus this dataset has been completely analysed successfully


