# Exno:1 Data Cleaning Process
### NAME : RIYA P L
### REG NO : 212223240141
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
df = pd.read_csv('Data_set.csv')
df
```
<img width="2111" height="817" alt="image" src="https://github.com/user-attachments/assets/3812b09a-d883-4a7b-a977-8c32567e8768" />

```
df.info()
```
<img width="824" height="549" alt="image" src="https://github.com/user-attachments/assets/cbf46a90-7617-408c-8311-d94e0b31cdb8" />

```
df.describe()
```
<img width="1272" height="560" alt="image" src="https://github.com/user-attachments/assets/33ec73ba-4df4-413f-8930-400a846777a6" />

```
df.head(10)
```
<img width="2166" height="681" alt="image" src="https://github.com/user-attachments/assets/43bc8711-771d-4318-b0b3-dc5f3fecbd1b" />

```
df.tail(5)
```
<img width="2081" height="387" alt="image" src="https://github.com/user-attachments/assets/21d47ff9-e510-4fcd-a105-ec5779449065" />

```
df.shape
```
<img width="267" height="144" alt="image" src="https://github.com/user-attachments/assets/f53ba5fc-9809-4e0c-a18d-5433acb1767f" />

```
df.isnull()
```
<img width="1788" height="808" alt="image" src="https://github.com/user-attachments/assets/199a4e1c-6abf-43c1-8974-e4d6a6ea9d9f" />

```
df.notnull()
```
<img width="1785" height="809" alt="image" src="https://github.com/user-attachments/assets/536a38d5-f9f8-4a3a-9fe3-427ce9e3f652" />

```
df.isnull().sum()
```
<img width="480" height="354" alt="image" src="https://github.com/user-attachments/assets/140903e8-5b72-4342-91ff-d968fd64e383" />

```
df.dropna(axis=0)
```
<img width="2167" height="808" alt="image" src="https://github.com/user-attachments/assets/b82c8b41-cda4-435a-b76d-a663dd865368" />

```
df.dropna(axis=1)
```
<img width="792" height="812" alt="image" src="https://github.com/user-attachments/assets/2e619e0f-004c-4ba0-8ce0-164295b2c966" />

```
dfs = df[df['num_episodes']>20]
dfs
```
<img width="1931" height="1268" alt="image" src="https://github.com/user-attachments/assets/c44bedc4-301a-41b4-8b53-a1befee8c36e" />

```
df.fillna(0)
```
<img width="1907" height="713" alt="image" src="https://github.com/user-attachments/assets/8aab0203-e39f-4a55-af08-8bb411ae31f0" />

```
dfs = df[df['show_name'].str.startswith(('A','F'))&(df['num_episodes']>25)]
dfs
```
<img width="1907" height="178" alt="image" src="https://github.com/user-attachments/assets/d5cb8a91-292d-4925-ac74-87d7755f4d11" />

```
df.iloc[:3]
```
<img width="1883" height="212" alt="image" src="https://github.com/user-attachments/assets/31cf6451-cc22-4a5e-b773-4dd23e82ed04" />

```
df.iloc[:4]
```
<img width="1853" height="284" alt="image" src="https://github.com/user-attachments/assets/60c9756c-d56a-4c8e-8022-27f8d3cd0724" />

```
df.iloc[[1,3,5],[1,3,5]]
```
<img width="547" height="231" alt="image" src="https://github.com/user-attachments/assets/4e4dbb7f-944e-4eab-82ac-55fe41c6429a" />

```
df.fillna('sample value')
```
<img width="1933" height="728" alt="image" src="https://github.com/user-attachments/assets/0ab823b0-2c5e-4a0c-aad2-cc6152ca1e24" />

```
ffil = df.fillna(method = 'ffill')
ffil
```
<img width="1904" height="728" alt="image" src="https://github.com/user-attachments/assets/fa72af1c-d77f-4065-9a99-274c45e97f7e" />

```
bfil = df.fillna(method = 'bfill')
bfil
```
<img width="1918" height="722" alt="image" src="https://github.com/user-attachments/assets/1075c696-35ec-437a-830b-fdd9e0ce6e1b" />

```
m = df.num_episodes.mean()
m
```
<img width="389" height="136" alt="image" src="https://github.com/user-attachments/assets/f3dd1c0b-9876-45ad-b3a3-04acf755f607" />

```
m = df.fillna(df['num_episodes'].mean())
m
```
<img width="1902" height="729" alt="image" src="https://github.com/user-attachments/assets/ddab5bed-97b5-477b-9b8c-adb9f5f2bde2" />

```
fmean = df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
fmean
```
<img width="775" height="376" alt="image" src="https://github.com/user-attachments/assets/4c5e3ff1-1f9f-48e0-8d2e-3ca71d71d74a" />

```
df = pd.read_csv('SAMPLEIDS.csv')
df
```
<img width="1396" height="1211" alt="image" src="https://github.com/user-attachments/assets/3d42eb40-aff0-46ee-b830-3318c433c913" />

```
df.shape
```
<img width="218" height="110" alt="image" src="https://github.com/user-attachments/assets/37e225db-1bce-4dff-84a9-0e1a47fe3444" />

```
df.describe()
```
<img width="1248" height="503" alt="image" src="https://github.com/user-attachments/assets/7c83d90f-d278-4a54-a0a3-ba95af91b315" />

```
df['GENDER'].value_counts()
```
<img width="373" height="136" alt="image" src="https://github.com/user-attachments/assets/9991c8ff-be45-4bbc-a596-4eade9d3686d" />

```
x1 = df.dropna(how='any')
x1
```
<img width="1371" height="763" alt="image" src="https://github.com/user-attachments/assets/e8233e41-c849-4231-b4d9-9715e7645391" />

```
res = df.dropna(subset=['M1','M2','M3','M4'],how='any')
res
```
<img width="1363" height="769" alt="image" src="https://github.com/user-attachments/assets/ea27b9c2-81d2-47c5-b093-c05a8067e620" />

## IQR(Inter Quartile Range)
```
df=pd.read_csv('heights.csv')
df
```
<img width="307" height="808" alt="image" src="https://github.com/user-attachments/assets/475bb4f3-98e9-4f03-84be-142f01c3b83a" />

```
sns.boxplot(data=df)
```
<img width="1064" height="785" alt="image" src="https://github.com/user-attachments/assets/babce550-9484-4ed8-bec6-356e925b7305" />

```
sns.scatterplot(data=df)
```
<img width="1021" height="778" alt="image" src="https://github.com/user-attachments/assets/966c3bae-99af-40fa-8a26-c1411efb1373" />

```
max = df['height'].quantile(0.75)
min = df['height'].quantile(0.25)
iqr = max-min
iqr
```
<img width="410" height="43" alt="image" src="https://github.com/user-attachments/assets/20d499d9-e76a-40fe-8c57-5e1fa3a5046a" />

```
lb = min-1.5*iqr
ub = max+1.5*iqr
outliers = df[(df['height']<lb)|(df['height']>ub)]
print("Lower bound:",lb)
print("Upper bound:",ub)
print("Outliers:",outliers)
```
<img width="445" height="165" alt="image" src="https://github.com/user-attachments/assets/5c3f98e7-944e-4a9f-9c64-990518970ad7" />

```
max = df['height'].quantile(0.75)
q2 = df['height'].quantile(0.5)
min = df['height'].quantile(0.25)
iqr = max-min
lb = min-1.5*iqr
ub = max+1.5*iqr
dfs = df[(df['height']>=lb)&(df['height']<=ub)]
dfs
```
<img width="300" height="711" alt="image" src="https://github.com/user-attachments/assets/9bb03cb9-1efd-454b-8e72-9cb64a8729c2" />

```
import numpy as np
from scipy import stats
z = np.abs(stats.zscore(df['height']))
z
```
<img width="877" height="99" alt="image" src="https://github.com/user-attachments/assets/a2b3fa09-7474-41f2-90a9-840ba7a78667" />

```
df1 = df[z<3]
df1
```
<img width="304" height="775" alt="image" src="https://github.com/user-attachments/assets/5cdbe964-ee94-4f91-8ea5-567be789f13a" />


# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
