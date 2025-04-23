# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS (1).csv")
df
```
![image](https://github.com/user-attachments/assets/1512d44b-0a70-4cc8-b1c3-6acac9aa4c4b)
![image](https://github.com/user-attachments/assets/b894bf74-78c5-43c9-90e3-470f754b4225)
```
df.info()
```
![image](https://github.com/user-attachments/assets/7b7424c1-154c-4322-988e-78e2ad110dc5)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/4067a0ef-5023-4964-8b97-a432387912f4)
```
df.shape
```
![image](https://github.com/user-attachments/assets/bea982d8-b750-469c-a643-24ba7e2ccce7)
```
df.head(10)
```
![image](https://github.com/user-attachments/assets/0951f338-3bb0-47b1-a7e9-366014c8054e)
```
df.tail(10)
```
![image](https://github.com/user-attachments/assets/1584cca7-257c-4244-a69c-a7934e065992)
```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/4dd64216-091b-45ef-985f-dc7a781e7bf1)
```
df.dropna(how='any').shape
```
![image](https://github.com/user-attachments/assets/bcc1a095-370d-4874-b871-f55af5d00eed)
```
df.shape
```
![image](https://github.com/user-attachments/assets/99a9ceb0-cdab-4aaf-96a0-954702786e6b)
```
x=df.dropna(how='any')
x
```
![image](https://github.com/user-attachments/assets/c23d9606-7f1a-447d-9993-d41c877244d9)
```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/user-attachments/assets/b0f1d1cf-1f09-47d6-8d32-b0a75215e479)
```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/user-attachments/assets/25278d15-b581-4e2b-b97f-ed310dd46d97)
![image](https://github.com/user-attachments/assets/8990d96d-5e56-439b-be3f-25736997879b)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/42701fe2-916b-4f6e-9846-da1a8ae573a8)
```
df.M1.fillna(method='ffill',inplace=True)
df
```
![image](https://github.com/user-attachments/assets/f333e5b5-8f1d-46ef-ba32-b3745f61e780)
![image](https://github.com/user-attachments/assets/ae325162-25bd-491c-942d-f64d931e5fea)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/9c2d5874-4ce8-4c94-979e-d7def58e0c35)
```
df.M2.fillna(method='ffill',inplace=True)
df
```
![image](https://github.com/user-attachments/assets/3e4b33da-ee73-4dd4-92c3-3f49a3d5305c)
![image](https://github.com/user-attachments/assets/5e7615f9-b03f-4234-94c9-8c1a1593c1c7)
```
df.isna().sum()
```
![image](https://github.com/user-attachments/assets/258eb283-cefe-43d4-8bba-034b2d11c98c)
```
df.M3.fillna(method='ffill',inplace=True)
df
```
![image](https://github.com/user-attachments/assets/c4c1d3ed-906d-475e-b319-062566c0083a)
![image](https://github.com/user-attachments/assets/597bcdf5-9afd-4b85-a6b9-1e22d5c9769f)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/8394651e-5469-4848-8702-c24f20287435)
```
df.duplicated()
```
![image](https://github.com/user-attachments/assets/f32d9449-3104-4250-bf12-f7835245764e)
![image](https://github.com/user-attachments/assets/c9a98b72-9f41-4487-a6e7-e77b5d97c8bd)
```
df.drop_duplicates(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/7d8967fd-c134-4c69-8de3-4dbe96b93b63)
![image](https://github.com/user-attachments/assets/bc203ccb-c6e9-4380-90d5-763cf28c25ee)
```
df.duplicated()
```
![image](https://github.com/user-attachments/assets/cf5a78d2-678b-4f2d-9cea-3ee23fd325f0)
![image](https://github.com/user-attachments/assets/922d4de4-ed1f-417a-afb4-6635f906fd7d)
```
df['DOB']
```
![image](https://github.com/user-attachments/assets/3a18b018-f4ad-4c3e-a233-e7a062f91968)
![image](https://github.com/user-attachments/assets/236f8a41-1f40-4880-a076-8a4224819cb4)
```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/user-attachments/assets/cf3b3a04-a0bb-4faf-ad66-f83c8d64c79b)
```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True);
```
![image](https://github.com/user-attachments/assets/cd821e9b-a047-4229-8ac1-aba4cb11a5d0)
```
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(age)
df
```
![image](https://github.com/user-attachments/assets/a538ac79-86b9-402b-bc46-896bb64c43d3)
```
sns.boxplot(data=df)
```
![image](https://github.com/user-attachments/assets/22fa9c15-21e4-4d35-894c-cd424470b051)
```
sns.scatterplot(data=df)
```
![image](https://github.com/user-attachments/assets/66bde7b4-92f2-495b-983d-a55a6e96a51e)
```
q1= df.quantile(0.25)
q2= df.quantile(0.5)
q3 = df.quantile(0.75)
iqr= q3-q1
iqr
```
![image](https://github.com/user-attachments/assets/2fe5e127-c715-4116-9b76-32205b88056e)
```
Q1=np.percentile(df,25)
Q3=np.percentile(df,75)
IQR=Q3-Q1
IQR
```
![image](https://github.com/user-attachments/assets/7e333b70-91dc-4a8c-92f7-6f89ad4dcecc)
```
lower_bound= Q1-1.5*IQR
upper_bound= Q3+1.5*IQR
lower_bound
```
![image](https://github.com/user-attachments/assets/dc2ded26-184c-4fd6-bc11-7f03cebe7645)
```
upper_bound
```
![image](https://github.com/user-attachments/assets/e9d873c6-5f62-460e-99fa-dd469bfc03c0)
```
outliers=[x for x in age if x<lower_bound or x>upper_bound]
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower Bound:",lower_bound)
print("Upper Bound:",upper_bound)
print("Outliers:",outliers)
```
![image](https://github.com/user-attachments/assets/61018181-f423-4cf1-af54-c434b20eabef)
```
df=df[((df>=lower_bound)&(df<=upper_bound))]
df
```
![image](https://github.com/user-attachments/assets/b9641c64-0185-4fd6-bd07-6675d7b74e61)
```
df=df.dropna()
df
```
![image](https://github.com/user-attachments/assets/68ef4703-213c-4e57-868d-0fcf1c783555)
```
sns.boxplot(data=df)
```
![image](https://github.com/user-attachments/assets/5143c498-085e-44d4-92f9-87dddb2bc82c)
```
sns.scatterplot(data=df)
```
![image](https://github.com/user-attachments/assets/8b564977-7be7-4ee5-93b5-e38f5a0a1559)
```
data=[1,2,2,2,3,1,1,15,2,2,2,3,1,1,2]
mean=np.mean(data)
std=np.std(data)
print('mean of the dataset is ',mean)
print('std.deviation is ',std)
```
![image](https://github.com/user-attachments/assets/21a97f4f-d9de-48cf-b5d4-5815433b13b2)
```
threshold=3
outlier=[]
for i in data:
  z=(i-mean)/std
  if(z>threshold):
    outlier.append(i)
print('outlier in dataset is',outlier)
```
![image](https://github.com/user-attachments/assets/e185dd2f-eb51-4680-9b8a-88ba3b404fca)
```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df1=pd.DataFrame(data)
df1
```
![image](https://github.com/user-attachments/assets/160ce398-7c70-46de-96dc-1d11a45c0b32)
![image](https://github.com/user-attachments/assets/21f26806-f9a1-4e47-a698-20f9f1ef7d96)
```
z=np.abs(stats.zscore(df1))
print(df1[z['weight']>3])
```
![image](https://github.com/user-attachments/assets/f9a4c922-469e-43c6-b008-72db89f65cb4)


# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method
