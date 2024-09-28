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
dt=pd.read_csv("titanic_dataset.csv")
dt
```

## OUTPUT
![image](https://github.com/user-attachments/assets/f9830642-84d0-44c8-a853-93bdbd6c1d4c)

```
dt.info()
```

## OUTPUT
![image](https://github.com/user-attachments/assets/ad17b358-59a9-402a-bfd3-a5902c1c0fff)

```
dt.shape
```

## OUTPUT
![image](https://github.com/user-attachments/assets/363686eb-b993-4be7-ad10-b6e9d2d1e042)

```
dt
```

## OUTPUT
![image](https://github.com/user-attachments/assets/fe3b1017-7e97-4661-b49b-938c5d068206)

```
dt.describe()
```

## OUTPUT
![image](https://github.com/user-attachments/assets/c99a52c5-4a32-4bf2-818e-09813f7c29df)
```
dt.nunique()
```
## OUTPUT
![image](https://github.com/user-attachments/assets/1d7cb173-693a-4aca-9910-d3b93b08424c)

```
dt["Survived"].value_counts()
```

## OUTPUT
![image](https://github.com/user-attachments/assets/cd68f1bf-488d-4848-88db-9cf5667c07ff)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

## OUTPUT
![image](https://github.com/user-attachments/assets/cfe2695c-a5cc-475f-a215-7f19d3932cc1)

```
sns.countplot(data=dt,x="Survived")
```

## OUTPUT
![image](https://github.com/user-attachments/assets/2c756d75-7b8c-4d30-9dc0-be869a5e8844)

```
dt.Pclass.unique()
```

## OUTPUT
![image](https://github.com/user-attachments/assets/f4603493-48de-44cb-a4ea-95fc797ae327)

```
dt.rename(columns={"Sex":"Gender"},inplace=True)
dt
```

## OUTPUT
![image](https://github.com/user-attachments/assets/5ed7b7bb-fbee-42c5-adc7-36aa0d043824)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

## OUTPUT
![image](https://github.com/user-attachments/assets/5f94cc6b-7ec7-4a3f-8011-c8bbf7e6caa6)

```
sns.catplot(x="Survived",hue='Gender',data=dt,kind='count')
```

## OUTPUT
![image](https://github.com/user-attachments/assets/8ad08d6e-4745-437a-b71b-426bf1491eb3)

```
dt.boxplot(column="Age",by="Survived")
```

## OUTPUT
![image](https://github.com/user-attachments/assets/314d9183-5e13-4c92-8118-4c3a70d08fd2)

```
sns.scatterplot(data=dt,x="Age",y="Fare",hue="Survived")
```

## OUTPUT
![image](https://github.com/user-attachments/assets/0e995ecd-e9f4-407e-b79c-8a3cc9608c98)

```
sns.jointplot(data=dt,x="Age",y="Fare",hue="Survived")
```

## OUTPUT
![image](https://github.com/user-attachments/assets/d8730e06-2ab3-407d-806a-ce48744bd4cf)

```
sns.catplot(x="Gender",col="Survived",hue="Pclass",kind="count",data=dt)
```

## OUTPUT
![image](https://github.com/user-attachments/assets/0480de19-1f48-4b9d-8995-4f3bcde54e7e)

```
numeric_dt=dt.select_dtypes(exclude=[object])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
## OUTPUT
![image](https://github.com/user-attachments/assets/4d9e1ad5-5747-4f9c-b0ee-a076ac7ed21b)

```
sns.pairplot(dt)
```
## OUTPUT
![image](https://github.com/user-attachments/assets/a2635aa1-820d-4ce8-9b01-db270b34079a)



# RESULT
Thus, the program is executed successfully.
