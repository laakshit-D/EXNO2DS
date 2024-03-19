# EXNO2DS
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
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
NAME : LAAKSHIT D
Reg No : 212222230071
```
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic.csv")
dt
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/e06452cb-fff5-46d9-91e5-1e13daed721d)

```python
dt.info()
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/8bde848f-e44f-44a9-ac0f-e259f11c65a7)

```python
dt.set_index('PassengerId',inplace=True)
dt.describe()
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/813b0217-8139-4f0f-bb4c-7cef93046ca5)

```python
dt.shape
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/fe9f5eef-962b-4984-9f62-0928129a36d6)

### CATEGORICAL DATA ANALYSIS

```python
dt.nunique()
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/428f6980-9a18-48f0-9c0a-cc1f8090bee1)

```python
dt["Survived"].value_counts()
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/6b13cbf2-e40f-477b-854c-6b035f60eb08)

```python
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/c6951eef-9034-4f9f-9f1a-8724a018dbea)

#### UNIVARIATE ANALYSIS

```python
sns.countplot(data=dt,x="Survived")
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/07df1378-7f18-4d9d-b891-2f839ccb05b0)

```python
dt.Pclass.unique()
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/c421cbe0-9718-48cf-812a-266a17c27ff9)

```python
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/76377e69-143a-4fdf-937a-d3d0260ad75b)

#### BIVARIATE ANALYSIS

```python
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/5269a77c-0399-4250-aec3-228d0ab6d31c)

```python
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/cf409002-66a2-49c1-bab9-daed33d5d5f9)

```python
dt.boxplot(column="Age",by="Survived")
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/7de0dd77-83ba-47c1-aac4-292b6f552717)

```python
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/f44a4475-948b-4070-87e8-5b5c1cf03ea6)

```python
sns.jointplot(x=dt["Age"],y=dt["Fare"],data=dt)
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/73f0aaf9-cd78-411c-b8af-5e857c0db614)

#### MULTIVARIATE ANALYSIS

```python
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/8b2d554b-a089-4e15-8b76-29f26fe6f40f)

```python
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/570d378c-9f74-4ec8-9a20-df375e105912)

```python
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/4b2293e7-e5d7-41fe-b0b1-64c59e5cfd49)

```python
sns.pairplot(dt)
```

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/4de84806-e138-419d-b9d9-776f376baff5)

![image](https://github.com/SanjithaBolisetti/EXNO2DS/assets/119393633/b3426fc2-b11f-4178-a30e-064d6f3a37a3)

## RESULT
   Thus,Data Analyzing of the given dataset was successful.
