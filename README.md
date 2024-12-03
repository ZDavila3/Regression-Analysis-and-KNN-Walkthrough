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
## Examine your data
