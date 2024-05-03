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
```
print(df.describe())
```
![Screenshot 2024-05-03 152719](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/b9c3d849-bced-4e42-baa6-d17f0d87f29b)

```
df.isnull().sum()
```
![Screenshot 2024-05-03 152729](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/1e5b1a4e-16c8-4e4a-81a1-072835c9d5bd)

```
df.nunique()
```
![Screenshot 2024-05-03 152737](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/dc56b545-a857-4902-9b92-b9ff5be4c525)

```
mn=df.TOTAL.mean()
mn
```
![Screenshot 2024-05-03 152745](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/af854e51-d48b-47fb-9502-8ee5925d5f35)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![Screenshot 2024-05-03 152757](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/047962d1-b08c-4abd-bb32-a4c9ba3bb018)

```
min=df.M4.min()
min
```
![Screenshot 2024-05-03 152806](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/f1f98ccf-d37f-4b3e-a57c-2a00de02ae05)

```
df.M4.fillna(min,inplace=True)
df
```
![Screenshot 2024-05-03 152820](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/63bcdd93-007d-44c3-927b-f914e4ac697c)

```
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![Screenshot 2024-05-03 152830](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/17c0b2d5-3fef-44ea-865b-2e4b0011a71b)

```
sns.boxplot(data=af)
```
![Screenshot 2024-05-03 152838](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/a856a162-29c9-4f55-8e97-52ed215225aa)

```
sns.scatterplot(data=af)
```
![Screenshot 2024-05-03 152845](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/a176a38f-691b-4e12-bf22-f77bf6dbb7a1)

```
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![Screenshot 2024-05-03 152854](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/efd9476a-3c35-449f-a956-470d29e7722f)

```
af=af[((af>=low)&(af<=high))]
af
```
![Screenshot 2024-05-03 152906](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/afb49c68-735b-4537-8dec-4cc1a31e2a79)

```
af.dropna()
```
![Screenshot 2024-05-03 152915](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/9aebb78b-ca0f-4c9e-80ed-92789382b8bc)

```
sns.boxplot(data=af)
```
![Screenshot 2024-05-03 152923](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/e59a3767-e224-46da-9134-7944f5d98bb9)

```
sns.scatterplot(data=af)
```
![Screenshot 2024-05-03 152932](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/c5b2d9d4-6f29-4299-a335-3d1a351a0e12)

```
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```
![Screenshot 2024-05-03 152947](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/735bd6c4-19b9-40f7-aaef-363766d1871b)

```
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![Screenshot 2024-05-03 152958](https://github.com/Harsayazheni/Expt01-Introduction-to-Data-Science/assets/118708467/1baea697-a825-4f87-993f-f11e0a197fe4)

# Result
Hence the data was cleaned , outliers were detected and removed.
