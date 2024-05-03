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
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![Screenshot 2024-05-03 152035](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/6caa894c-4fe2-4654-9290-b183df67885a)

```
print(df.head(7))
```
![Screenshot 2024-05-03 152057](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/67ef2321-c7b9-45a5-80af-726060e9e6ba)
```
print(df.tail(2))
```
![Screenshot 2024-05-03 152149](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/91afca65-47fa-4e01-8b93-c7da6c9cc6b8)
```
df.info()
```
![Screenshot 2024-05-03 152234](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/0457f93e-3e62-489a-a43c-5eaf6b2907f8)

# Result
          <<include your Result here>>
