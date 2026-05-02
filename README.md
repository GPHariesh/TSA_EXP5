# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 02-05-2026
## NAME : G P HARIESH
## REG.NO : 212224040100


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.
## REQUIREMENTS
Dataset : salesdata.csv
Software : google colab

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

data = pd.read_csv("sales_data.csv",
                   parse_dates=['Sale_Date'])

data = data.sort_values('Sale_Date')
data.set_index('Sale_Date', inplace=True)

X = data['Unit_Price']

decomposition = seasonal_decompose(X, model='additive', period=12)

plt.figure(figsize=(10,12))

plt.subplot(411)
plt.plot(X, label='Unit Price')
plt.legend(loc='upper left')
plt.title('Unit Price Data')

plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Trend Plot')

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
<img width="824" height="497" alt="image" src="https://github.com/user-attachments/assets/20db5389-a2d0-4adc-9b26-5a236fb43a1d" />
<img width="822" height="491" alt="image" src="https://github.com/user-attachments/assets/188981e1-ffa1-4140-a72e-bc92f2dbbceb" />





### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
