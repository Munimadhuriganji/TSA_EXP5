# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 19-09-2025
#### NAME:GANJI MUNI MADHURI
#### REGISTER NUMBER:212223230060

### AIM:
To Illustrates how to perform time series analysis and decomposition.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Load the dataset, Convert 'date' column to datetime format, Set it as index
data = pd.read_csv('/content/ABB_15minute.csv', parse_dates=['date'], index_col='date')

# Step 2: Perform seasonal decomposition using the correct column name
decomposition = seasonal_decompose(data['open'], model='additive', period=12)

# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))  # Adjust the figure size

# Original Data
plt.subplot(411)
plt.plot(data['open'], label='open')
plt.legend(loc='upper left')
plt.title('Open Prices')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residuals')

plt.tight_layout()
plt.show()

```

### OUTPUT:

PLOTTING THE DATA:
<img width="1235" height="375" alt="image" src="https://github.com/user-attachments/assets/91006b95-8c32-4811-a33b-abffb52913e4" />

LINEAR TREND PLOT:
<img width="1222" height="366" alt="image" src="https://github.com/user-attachments/assets/7567347c-3a53-45e7-a755-abf78b78831e" />

SEASONAL PLOT REPRESENTATION :
<img width="1228" height="361" alt="image" src="https://github.com/user-attachments/assets/b6fe7b68-4a30-46a8-81f9-b214ff7ae773" />


RESIDUAL PLOT:
<img width="1221" height="358" alt="image" src="https://github.com/user-attachments/assets/d95c839a-0956-404e-a7d4-d8c25fb95edf" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
