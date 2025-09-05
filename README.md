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
# code
```
df.head()
```
<img width="908" height="212" alt="image" src="https://github.com/user-attachments/assets/dd92b9ee-09f0-4430-a516-9f0c96814b3b" />


# Result
          <<include your Result here>>
