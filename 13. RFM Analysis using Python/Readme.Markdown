

# RFM Analysis Project

## Overview
This project focuses on RFM (Recency, Frequency, Monetary) Analysis, a widely used technique in the marketing domain for understanding and segmenting customers based on their buying behavior. The dataset for this analysis is sourced from [here](https://statso.io/rfm-analysis-case-study/).

RFM Analysis helps businesses assess customers’:
- **Recency**: The date they made their last purchase.
- **Frequency**: How often they make purchases.
- **Monetary Value**: The amount spent on purchases.

## Project Structure
The project is organized as follows:
1. **Data Preprocessing**
   - Loading the dataset.
   - Converting purchase dates to datetime format.
   - Calculating Recency, Frequency, and Monetary values for each customer.

2. **RFM Calculation**
   - **Recency**: Calculated as the number of days since the customer's last purchase.
   - **Frequency**: The total number of purchases made by each customer.
   - **Monetary Value**: The total amount spent by each customer.

3. **Customer Segmentation**
   - Segmenting customers based on their RFM scores.
   - Analyzing and interpreting the segments.

## Notable Code Snippets

### Data Loading and Preprocessing
```python
import pandas as pd
from datetime import datetime

# Load the data
data = pd.read_csv('path_to_your_data.csv')

# Convert 'PurchaseDate' to datetime
data['PurchaseDate'] = pd.to_datetime(data['PurchaseDate'])

# Calculate Recency
data['Recency'] = (datetime.now() - data['PurchaseDate']).dt.days

# Calculate Frequency
frequency_data = data.groupby('CustomerID')['OrderID'].count().reset_index()
frequency_data.rename(columns={'OrderID': 'Frequency'}, inplace=True)
data = data.merge(frequency_data, on='CustomerID', how='left')

# Calculate Monetary Value
monetary_data = data.groupby('CustomerID')['TransactionAmount'].sum().reset_index()
monetary_data.rename(columns={'TransactionAmount': 'MonetaryValue'}, inplace=True)
data = data.merge(monetary_data, on='CustomerID', how='left')
```

### Segment Scores Calculation
```python
segment_scores = data.groupby('RFM Customer Segments')[['RecencyScore', 'FrequencyScore', 'MonetaryScore']].mean().reset_index()
```

### Custom Order for Segments
```python
custom_order = ['Champions', 'Potential Loyalists', 'At Risk Customers', 'Can\'t Lose', 'Lost']
segment_scores['RFM Customer Segments'] = pd.Categorical(segment_scores['RFM Customer Segments'], categories=custom_order, ordered=True)
segment_scores = segment_scores.sort_values('RFM Customer Segments').reset_index(drop=True)
```

## Results
The project resulted in meaningful customer segments, which can be used for targeted marketing strategies. The segments are ordered and analyzed based on their RFM scores, helping in identifying key customer behaviors and engagement levels.

## Conclusion
This RFM Analysis project demonstrates the process of calculating and interpreting RFM metrics to segment customers effectively. These insights can drive data-driven marketing strategies, enhancing customer engagement and loyalty.