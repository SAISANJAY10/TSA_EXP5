# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION

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
import statsmodels.api as sm
from statsmodels.tsa.seasonal import seasonal_decompose

data = sm.datasets.sunspots.load_pandas().data

data.head()

decomposition = seasonal_decompose(data['SUNACTIVITY'], model='additive',period=12)

plt.figure(figsize=(10, 12))
plt.subplot(411)
plt.plot(data['SUNACTIVITY'], label='Sun Activity')
plt.legend(loc='upper left')
plt.title('Sun Activity')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')

plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()

```
### OUTPUT:

FIRST FIVE ROWS:

<img width="239" height="260" alt="image" src="https://github.com/user-attachments/assets/7524b462-6efa-418c-b930-bb25b2a18a85" />

PLOTTING THE DATA:

<img width="1054" height="325" alt="image" src="https://github.com/user-attachments/assets/95e630c4-4eab-4fe5-8ecf-a6e24af36029" />

SEASONAL PLOT REPRESENTATION :

<img width="697" height="179" alt="image" src="https://github.com/user-attachments/assets/17a3ea95-549b-432a-a2e0-dcba885a9ff8" />

TREND PLOT REPRESENTATION :

<img width="716" height="182" alt="image" src="https://github.com/user-attachments/assets/f6d03479-f1ac-4877-8cc2-ec59dd56d947" />

OVERALL REPRESENTATION:

<img width="797" height="173" alt="image" src="https://github.com/user-attachments/assets/8ab04039-9d41-4c0f-894c-9f391871e3ad" />

### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
