# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 24/02/2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

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
# Step 1: Load the dataset,Convert 'Month' column to datetime format,Set it as index
data = pd.read_csv('NSE-TATAGLOBAL11.csv',parse_dates=['Date'],index_col='Date')
# Step 2: Perform seasonal decomposition using the correct column name
decomposition = seasonal_decompose(data['Turnover (Lacs)'], model='additive',period=12)
# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))  # Adjust the figure size for a square shape
# decomposition.plot() this plots all four of teh following graphs
# Original Data
plt.subplot(411)
plt.plot(data['Turnover (Lacs)'], label='Turnover')
plt.legend(loc='upper left')
plt.title('Turnover (Lacs)')
# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')
# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')
# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
```

### OUTPUT:


<img width="685" height="181" alt="image" src="https://github.com/user-attachments/assets/d5057e18-5b0d-43ae-81ee-740a47a2404e" />



<img width="655" height="185" alt="image" src="https://github.com/user-attachments/assets/137f1d05-356b-4d8c-ae77-8468c7f52f80" />



<img width="616" height="182" alt="image" src="https://github.com/user-attachments/assets/1c6bc2af-2fe6-44ae-8260-ac957fbec684" />



<img width="678" height="151" alt="image" src="https://github.com/user-attachments/assets/3fd36832-5033-4c0f-9919-88dc1f8b0914" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
