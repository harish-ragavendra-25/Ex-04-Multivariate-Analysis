# Ex-04-Multivariate-Analysis

#AIM:
write a python program to visualize the given data by analysing the multivariables in data

#algorithm:

#step1:
import the csv file using pandas package.
#step2:
store the data as dataframe in a variable.
#step3:
display the information of data sunch as datatypes,value counts,skewness
#step4:
display the data in the barplot,scatter plot and heatmap

#code:

```
import pandas as pd 
import seaborn as sns
from matplotlib import pyplot as plt
df=pd.read_csv('SuperStore.csv')
df.info()
```
```
df.dtypes
df['State'].value_counts()
df.describe()
df.kurtosis()
```
```
sns.scatterplot(x=df['Postal Code'],y=df['Sales'])
```
```
sns.barplot(x=df['Postal Code'],y=df['Sales'])
```
```
df.info()
```
```
postal=df.loc[:,["Sales","Postal Code"]]
postal=postal.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")
sns.barplot(x=postal.index,y="Sales",data=postal)
plt.xticks(rotation=90)
plt.xlabel=("Postal")
plt.ylabel=("Sales")
plt.show()
```
```
sns.heatmap(df.corr())
```

##output:

![Screenshot from 2023-04-04 22-40-32](https://user-images.githubusercontent.com/114852180/229866691-ef1373c6-a66e-451a-8ebc-ba22abb25ee2.png)
![Screenshot from 2023-04-04 22-41-53](https://user-images.githubusercontent.com/114852180/229867072-05b452c2-d7b9-462e-820c-a54f680b578a.png)
![Screenshot from 2023-04-04 22-43-08](https://user-im![Screenshot from 2023-04-04 22-43-08](https://user-ages.githubusercontent.com/114852180/229867794-d32092b0-a9dd-43a2-8667-6f186afecf2b.png)
![Screenshot from 2023-04-04 22-43-08](https://user-images.githubusercontent.com/114852180/229868374-650d6aa8-8b42-4f42-a098-e249f3138c10.png)
![Screenshot from 2023-04-04 22-50-56](https://user-images.githubusercontent.com/114852180/229869371-d6a6a8e3-f6fa-4428-9837-b89833e2dc34.png)
![Screenshot from 2023-04-04 22-52-09](https://user-images.githubusercontent.com/114852180/229869640-5032e76f-ae89-447d-82a6-4b46077d38db.png)
![Screenshot from 2023-04-04 22-54-38](https://user-images.githubusercontent.com/114852180/229872246-8c82960f-b50f-48fe-9a01-273ff98786a6.png)
![Screenshot from 2023-04-04 22-58-48](https://user-images.githubusercontent.com/114852180/229872323-1738e2b3-578e-449b-a553-ff2277109d7d.png)

##RESULT:

thus the experiment executed sucessfully.
