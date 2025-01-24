![image](https://github.com/user-attachments/assets/ac7eb556-9d83-4b2e-8c09-b9a0dfd6869e)

## What is data cleaning? 
Data cleaning, also known as data cleansing or data scrubbing, is the process of identifying and correcting (or removing) errors, inconsistencies, and inaccuracies within a dataset.

The importance of data cleaning lies in the following factors:

- Improved data quality: It is therefore very important to clean the data as this reduces the chances of errors, inconsistencies and missing values, which ultimately makes the data to be more accurate and reliable in the analysis.
- Better decision-making: Consistent and clean data gives organization insight into comprehensive and actual information and minimizes the way such organizations make decisions on outdated and incomplete data.
- Increased efficiency: High quality data is efficient to analyze, model or report on it, whereas clean data often avoids a lot of foreseen time and effort that goes into handling poor data quality.


| Common Data Quality Issues | Example                |
|----------------------------| -------------------------- |
| Missing Values             | Absence of a value in a dataset. |
| Duplicate Data | Identical or nearly identical records appearing multiple times in a dataset. |
| Incorrect Data Type | String data represented as Int data type | 
| Formatting Inconsistencies | Creating a standardized date format and capitalization.|
|Outliers and Anomalies | Observations whose values are unusually high or low compared to other observations|
| Spelling / Typographical Errors | Misspelling and typos can occur in qualitative data |


## Common Python libraries used for general-purpose data cleaning

### Pandas

  Key Features for Data Cleaning:
- Handling Missing Data: `isnull()`, `dropna()`, `fillna()`.
- Removing Duplicates: `duplicated()`, `drop_duplicates()`.
- Data Type Conversion: `astype()`.
- Filtering and Subsetting Data: Boolean indexing, `query()`.
- String Operations: `str.contains()`, `str.replace()` for cleaning text data.

### NumPy - A fundamental package for numerical computations, often used with pandas for more advanced operations.

  Key Features for Data Cleaning:
- Handling Missing Data: NumPy arrays represent missing values as `np.nan`.
- Data Transformation: Apply mathematical or logical operations efficiently.
- Filtering Data: Boolean masks.

 How to install NumPy? 

In terminal, run the following command:
```Powershell
  pip install numpy
```

## Implementing data cleaning funtions

### Dropping Duplicates 

```Python
df.drop_duplicates(inplace=True)
```

### Locating zero's 

```Python
df.loc[(df==0).any(axis=1)]
```
#### Example of locating zero's in a particular column..
```Python
df.loc[(df==0).any(axis=1)]
columns_to_check = ['Column1Name', 'Column2Name', 'Column3Name', 'Column4Name']
#Replaces 0 with NAN (Not a Number) --> this is optional 
df[columns_to_check] = df[columns_to_check].replace(0, np.nan)
#prints out the number of 0's after being replaces with NAN's
print(df.isna().sum())
```

### .astype() - Changing a columns data type (ie. from string to int)
```Python
df['column6name'] = df['column6name'].astype(int)
```
