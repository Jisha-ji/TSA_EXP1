# Ex.No: 01A PLOT A TIME SERIES DATA
# Date: 20-04-2026

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.

# Software Required:

Google colab

# Dataset:

stock_data.csv

# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:

```
from matplotlib import pyplot as plt
import pandas as pd

df = pd.read_excel("/content/stock_data.csv")

df.iloc[:, 0] = pd.to_datetime(df.iloc[:, 0])

df.rename(columns={df.columns[0]: 'Date'}, inplace=True)

df.set_index('Date', inplace=True)


df_resampled = df['Stock_1'].resample('D').interpolate()


df_resampled.plot(kind='line', label='Stock 1', color='black')

plt.title('Time Series Plot of Stock 1')
plt.xlabel('Day')
plt.ylabel('Stock Price')
plt.legend()
plt.grid(True)
plt.show()

```
# OUTPUT:

<img width="818" height="541" alt="image" src="https://github.com/user-attachments/assets/e9f28edc-a1fa-4472-9a2c-06dcd34e7f9d" />


# RESULT:
Thus we have created the python code for plotting the time series of given data.
