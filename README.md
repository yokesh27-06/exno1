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
import numpy as np
df=pd.read_csv("SAMPLEIDS.csv")
df
```
<img width="1038" height="851" alt="Screenshot 2025-09-01 041620" src="https://github.com/user-attachments/assets/9dd9deaf-298e-411f-9454-7865d9555228" />


```
df.head()
```
<img width="1052" height="253" alt="Screenshot 2025-09-01 041845" src="https://github.com/user-attachments/assets/61296980-0a3a-4193-ab55-c0ae827ddd6b" />

```
df.tail
```
<img width="909" height="213" alt="Screenshot 2025-09-06 085432" src="https://github.com/user-attachments/assets/aa9095ae-5307-444a-908b-d4e571a3bb6d" />

```
df.isnull()
```
<img width="868" height="862" alt="image" src="https://github.com/user-attachments/assets/091c10ff-ecd8-4192-83c8-684bcc6bdb15" />

```
df.fillna(method='ffill')
```
<img width="1027" height="868" alt="image" src="https://github.com/user-attachments/assets/0586d022-b6d9-41ce-bce7-f13beaaf8a42" />

```
df.fillna(0)
```
<img width="1020" height="869" alt="Screenshot 2025-09-06 091655" src="https://github.com/user-attachments/assets/d38e83da-9da3-4a0e-80d1-d21755d74290" />

```
df.dropna(axis=0)
```
<img width="1023" height="552" alt="image" src="https://github.com/user-attachments/assets/ae740f93-3ea4-4b6b-8bb0-7e55d0b92d0a" />

```
df.isnull().any()
```
<img width="266" height="567" alt="image" src="https://github.com/user-attachments/assets/389fed69-c5a2-4de2-8134-c6c14ccea780" />

```
df.isnull().sum()
```
<img width="220" height="572" alt="image" src="https://github.com/user-attachments/assets/1b694aa6-4b7c-4e6a-8493-88a51f9628f7" />

```
df.notnull()
```
<img width="866" height="862" alt="image" src="https://github.com/user-attachments/assets/ab4a4c1f-42ff-4ba7-823f-d59054774037" />

```
df.isnull()
```
<img width="842" height="857" alt="image" src="https://github.com/user-attachments/assets/cbd525b8-65f4-4c20-901b-434aaf76ec7f" />

```
df.fillna({'GENDER':'MALE','NAME':'SRI'})
```
<img width="1047" height="852" alt="image" src="https://github.com/user-attachments/assets/0a903518-5a55-4745-8ec2-a240a5605ef1" />

```
dhinesh=pd.read_csv("SAMPLEIDS.csv")
dhinesh
```
<img width="1047" height="863" alt="image" src="https://github.com/user-attachments/assets/665449fd-0f21-411b-af79-41806675c135" />

```
dhinesh.describe()
```
<img width="931" height="361" alt="image" src="https://github.com/user-attachments/assets/d01f1507-7a5e-464f-8f77-b423fdb20d09" />

```
dhinesh=pd.read_csv('iris.csv')
dhinesh
```
<img width="657" height="508" alt="image" src="https://github.com/user-attachments/assets/522253f6-852a-40fc-98ee-b82e242de13a" />

```
dhinesh.describe()
```
<img width="588" height="362" alt="image" src="https://github.com/user-attachments/assets/cc26a91e-4aee-4e24-8432-6908f62f01dd" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=dhinesh)
```
<img width="665" height="571" alt="image" src="https://github.com/user-attachments/assets/a2eaa9a2-1f89-4282-a12a-47296fcb141d" />

```
q1=dhinesh.sepal_width.quantile(0.25)
q3=dhinesh.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```
<img width="123" height="55" alt="image" src="https://github.com/user-attachments/assets/1fd9b0c7-5680-41f1-86cc-491156812a8d" />

```
rid=dhinesh[((dhinesh.sepal_width<(q1-1.5*iqr)) | (dhinesh.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
<img width="202" height="256" alt="image" src="https://github.com/user-attachments/assets/279fce48-00d2-42e5-bf7d-45265cae9a94" />

```
delid=dhinesh[~((dhinesh.sepal_width<(q1-1.5*iqr)) | (dhinesh.sepal_width>(q3+1.5*iqr)))]
delid
```
<img width="655" height="517" alt="image" src="https://github.com/user-attachments/assets/ddd4461d-6e6b-4bba-aeb7-1f1d42d55fde" />

```
sns.boxplot(x='sepal_width',data=delid)
```
<img width="677" height="580" alt="image" src="https://github.com/user-attachments/assets/b6e33d3e-dfd6-4394-861e-07f3f31e59e4" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(dhinesh['sepal_width']))
z
```
<img width="653" height="653" alt="image" src="https://github.com/user-attachments/assets/c255af69-6b2e-4f78-8317-fc04593f1880" />

```
z1=z[z<3]
z1
```
<img width="657" height="650" alt="image" src="https://github.com/user-attachments/assets/562e364e-5c47-4faf-bfbf-be1a665c7a96" />
























# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.


