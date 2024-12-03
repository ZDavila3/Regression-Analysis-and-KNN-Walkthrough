## Loading Data Using Pandas

Pandas is widely-used open-source Python library for data manipulation and analysis. It provides data structures like DataFrame (df) and Series to handle data efficiently and offers a wide variety of functions to clean, transform, analyze, and visualize data. It is often used for tasks such as data loading, preparation, filtering, aggregation, and merging.

The name "Pandas" has a reference to both "Panel Data", and "Python Data Analysis" and was created by Wes McKinney in 2008.


Pandas gives you answers about the data. Like:

- Is there a correlation between two or more columns?
- What is average value?
- Max value?
- Min value?

Pandas are also able to delete rows that are not relevant, or contains wrong values, like empty or NULL values. This is called cleaning the data.

## How to install pandas? 
```Powershell
  pip install pandas
```
## Loading data with pandas
To load data using Pandas, you would typically use the `pandas.read_*` functions depending on the type of data file you are working with. 

Common Pandas Functions to Load Data:
- `pd.read_csv()`: Reads CSV files.
- `pd.read_excel()`: Reads Excel files.
- `pd.read_json()`: Reads JSON data.
- `pd.read_sql()`: Loads data from a SQL database.
- `pd.read_html()`: Reads tables from HTML pages.

Example code of uploading my data set called "Cows.csv"
```Python
import pandas as pd

df = pd.read_csv('Cows.csv')
df
```
## Examine your data using Panda functions!
In Pandas, there are several useful functions to inspect and understand your data once it is loaded into a DataFrame. Here are some of the most commonly used ones:
- `.head()` : By default, it shows the first 5 rows of your data set.
```Python
print(df.head()) # defaults to first five, input a nummber to customize like .head(10)
```
- `.tail()` : By default, it shows the last 5 rows of your data set.
```Python
print(df.tail()) # defaults to last five, input a nummber to customize like .tail(10)
```
- `.info()` : Provides a summary of the DataFrame, including the number of non-null entries, column names, data types, and memory usage.
```python
print(df.info())
```
- `.describe()` : Gives descriptive statistics for numerical columns, such as count, mean, standard deviation, min, max, and quartiles (25%, 50%, 75%)
```python
print(df.describe())
```
- `.shape` : Returns a tuple representing the dimensions of the DataFrame: (number of rows, number of columns).
```python
print(df.shape)  # (rows, columns)
```
- `.columns` : Returns a list of the column names in the DataFrame.
```python
print(df.columns)
```
- `.dtypes` : Returns the data types of each column in the DataFrame.
```python
print(df.dtypes)
```
- `.isnull()` : Returns a DataFrame of the same shape with True for missing values and False otherwise.
```python
print(df.isnull())
```
- `.isnull()` + `.sum()` : Can be used to count the number of missing values in each column.
```python
print(df.isnull().sum())  # Count of missing values in each column
```
- `.value_counts()` : Provides the frequency of unique values in a column, useful for categorical data.
```python
print(df['column_name'].value_counts())
```
- `.sample()` : Returns a random sample of rows from the DataFrame. Useful for getting a random subset of your data.
```python
print(df.sample(5))  # Randomly shows 5 rows
```
Learn more about Pandas built in functions: https://pandas.pydata.org/pandas-docs/stable/reference/general_functions.html
























https://pandas.pydata.org/docs/getting_started/overview.html
https://www.w3schools.com/python/pandas/pandas_intro.asp
