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














# Result
          <<include your Result here>>
