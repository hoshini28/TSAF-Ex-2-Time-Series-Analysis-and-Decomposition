# TSAF-Ex-2-Time-Series-Analysis-and-Decomposition

## AIM:
To perform time series analysis and decomposition on the monthly average temperature of a
city using Python.

We will use simple sample temperature data for 12 months and decompose it into:

Observed = Trend + Seasonal + Residual

## PROGRAM:

```
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Dataset 4: Monthly Hotel Occupancy Percentage (12 Months)
occupancy_rate = [
 42, 50, 65, 70, 82, 88,
 95, 91, 78, 60, 48, 72
]

# Create date index for 2025
dates = pd.date_range(start="2025-01-01", periods=12, freq="ME")

# Create time series
data = pd.Series(occupancy_rate, index=dates)
print("Monthly Hotel Occupancy Rate (%):")
print(data)

# Plot original series
plt.figure(figsize=(10, 5))
plt.plot(data.index, data.values, marker="d", color="purple")
plt.title("Hotel Occupancy Rate Analysis")
plt.xlabel("Month")
plt.ylabel("Occupancy (%)")
plt.grid(True)
plt.show()

# Decompose time series
result = seasonal_decompose(data, model="additive", period=12)
result.plot()
plt.show()

```

## OUTPUT:

<img width="773" height="601" alt="image" src="https://github.com/user-attachments/assets/4dc2ea8f-bfc6-4415-8243-b9066ddbeb12" />
