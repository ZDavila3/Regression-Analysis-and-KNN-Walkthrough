
## Filling/Replacing Outliers Statistically
### Remove outliers with quantiles 

##### Quantile-based methods are widely used in statistics to handle outliers and to make data more manageable and representative for analysis. By removing values below the 1st percentile and above the 99th percentile, you essentially filter out the most extreme outliers, which can help in creating a more robust and accurate analysis.

```Python
q_low = df['YOUR-DESIRED-COLUMN1'].quantile(0.01) #Calculate the lower quantile (1st percentile)
q_hi  = df['YOUR-DESIRED-COLUMN1'].quantile(0.99) #Calculate the upper quantile (99th percentile)
df[(df['YOUR-DESIRED-COLUMN1'] < q_hi)&(df['YOUR-DESIRED-COLUMN1'] > q_low)] #Filter the DataFrame to remove outliers
```

### Remove outliers with std

##### Standard Deviation: A measure of the dispersion or spread of a set of values. It quantifies the amount of variation or deviation from the mean. Empirical Rule: In a normal distribution:

-Approximately 68% of the data falls within one standard deviation of the mean.

-Approximately 95% of the data falls within two standard deviations of the mean.

-Approximately 99.7% of the data falls within three standard deviations of the mean.

By using three times the standard deviation as the threshold, you are essentially capturing around 99.7% of the data and considering the rest as outliers. This approach works well if your data is normally distributed.

``` Python
import numpy as np
ab = np.abs(df['YOUR-DESIRED-COLUMN1']-df['YOUR-DESIRED-COLUMN1'].mean()) #calculates the absolute difference between each value in the column and the mean. This gives us a measure of how far each value is from the mean.
std = (3*df['YOUR-DESIRED-COLUMN1'].std()) #This line calculates three times the standard deviation of the column
df[ab <= std ] #Filtering out outliers
```
Replacing Outliers with Median
Replace outliers with the median value to maintain the central tendency.
median = df['YOUR-DESIRED-COLUMN1'].median()
df.loc[(df['YOUR-DESIRED-COLUMN1'] < q_low) | (df['YOUR-DESIRED-COLUMN1'] > q_hi), 'YOUR-DESIRED-COLUMN1'] = median



Log Transformation
Applying a log transformation to reduce the effect of outliers and skewed data.
df['YOUR-DESIRED-COLUMN1'] = np.log(df['YOUR-DESIRED-COLUMN1'] + 1)  # Adding 1 to avoid log(0)
