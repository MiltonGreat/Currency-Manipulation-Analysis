# Currency Manipulation Analysis Project

Detecting Suspicious Exchange Rate Movements Using Anomaly Detection

### Project Overview

This project identifies potential currency manipulation or anomalous trading patterns by analyzing exchange rate data. Using statistical methods (Z-scores, rolling volatility), it flags extreme movements that deviate from historical trends, which could indicate market manipulation, data errors, or economic shocks.

### Dataset Overview

The dataset contains daily foreign exchange (FX) rates for multiple currencies against a base currency (e.g., EUR).

### Methodology

1. Data Cleaning & Validation
- Converted date to datetime format for time-series operations.
- Handled missing data: Filled missing currency_name with "Unknown".
- Removed duplicates based on currency, base_currency, and date.
- Flagged invalid codes: Ensured all currency values were 3-letter uppercase strings (e.g., ^[A-Z]{3}$).

2. Anomaly Detection
- Method: Rolling Z-scores on daily returns.
- Computed rolling statistics (30-day window)
- Flagged anomalies

3. Output & Visualization
- Exported anomalies: Saved 3,450 suspicious rows to suspicious_movements.csv.
- Plotted trends: Highlighted anomalies for specific currencies (e.g., AED):

### Results

Temporal Clustering:

- March–June 2024: 62% of AED anomalies occurred in this window, suggesting an external event (e.g., policy shift).
- ZWL: Anomalies evenly distributed, aligning with its inherent instability.

### Conclusion

This project demonstrated how statistical methods can surface potential currency manipulation. While the Z-score approach flagged 3,450 anomalies, further refinement (e.g., dynamic thresholds) could reduce noise. The results underscore the importance of domain knowledge—true manipulation requires validation against real-world events.

### Source

[Forex Exchange Rates Since 2004 Dataset from Kaggle](https://www.kaggle.com/datasets/asaniczka/forex-exchange-rate-since-2004-updated-daily)
