# Ex-04-Compute-ACF-for-the-First-35-Lags

## NAME : Paladugu Venkata Balaji
## REG NO : 2305001024
## Aim
To calculate and plot the Autocorrelation Function (ACF) for the first 35 lags of a time-series dataset and identify a suitable time-series model.

## Objectives
1. To create time-series data using Pandas.
2. To plot the original time series.
3. To calculate ACF values for the first 35 lags.
4. To display and plot the ACF values.
5. To identify possible AR, MA, or ARMA models based on the ACF pattern.
## Program

~~~python
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.stattools import acf
from statsmodels.graphics.tsaplots import plot_acf
data = [
    112, 118, 132, 129, 121, 135,
    148, 148, 136, 119, 104, 118,
    115, 126, 141, 135, 125, 149,
    170, 170, 158, 133, 114, 140,
    145, 150, 165, 160, 155, 170,
    190, 188, 175, 160, 145, 165,
    170, 180, 195, 190, 185, 200
]
series = pd.Series(data)
plt.figure(figsize=(10, 4))
plt.plot(series, marker="o")
plt.title("Time Series Data")
plt.xlabel("Time")
plt.ylabel("Value")
plt.grid(True)
plt.show()
acf_values = acf(series, nlags=35)
print("ACF Values:")
for lag, value in enumerate(acf_values):
    print("Lag", lag, ":", round(value, 4))
plt.figure(figsize=(12, 5))
plot_acf(series, lags=35)
plt.title("ACF for First 35 Lags")
plt.xlabel("Lag")
plt.ylabel("Autocorrelation")
plt.show()
~~~

## Output
<img width="1047" height="478" alt="image" src="https://github.com/user-attachments/assets/822a23c7-3a18-4e78-9fdf-a3cc4df13d7b" />
<img width="1022" height="813" alt="image" src="https://github.com/user-attachments/assets/d1be84c1-7c49-4258-9619-b85289f1c0d9" />

## Result
The Autocorrelation Function (ACF) was successfully calculated and plotted for the first 35 lags. The ACF pattern can help identify a suitable AR, MA, or ARMA model. PACF should also be examined to determine the model order more reliably.
