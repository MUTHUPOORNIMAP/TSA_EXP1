# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date: 26-10-2026

# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
```
import matplotlib.pyplot as plt
import pandas as pd

# Read the CSV file
df = pd.read_csv('/content/BMW_Car_Sales_Classification.csv')

# Display first five rows
df.head()

# Convert Year to datetime
df['Year'] = pd.to_datetime(df['Year'], format='%Y')

# Check data types
print(df.dtypes)

# Set Year as index
df.set_index('Year', inplace=True)

# Resample yearly sales volume
df_resampled = df['Sales_Volume'].resample('YS').mean().interpolate()

# Plot the resampled data
df_resampled.plot(
    kind='line',
    label='Sales Volume',
    color='black',
    marker='o'
)

plt.title('Time Series Plot of BMW Sales Volume Each Year')
plt.xlabel('Year')
plt.ylabel('Sales Volume')
plt.legend()
plt.grid(True)
plt.show()
```










# OUTPUT:

<img width="448" height="252" alt="image" src="https://github.com/user-attachments/assets/5d9e7110-8a2e-4829-b6c8-3fc43661b07d" />

<img width="727" height="497" alt="image" src="https://github.com/user-attachments/assets/cc77e3c1-bd2a-4665-82f4-bf9c75373e70" />




# RESULT:
Thus we have created the python code for plotting the time series of given data.
