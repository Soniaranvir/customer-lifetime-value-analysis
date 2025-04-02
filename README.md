# Customer Lifetime Value Analysis

## Overview
This project analyzes customer transaction data to estimate Customer Lifetime Value (CLV) using probabilistic models. It utilizes the `lifetimes` package to predict customer purchasing behavior and revenue potential.

## Dataset
The project uses an online retail dataset (`Online_Retail.xlsx`) that contains transactional data, including:
- **InvoiceNo**: Unique invoice identifier
- **StockCode**: Item identifier
- **Description**: Item name
- **Quantity**: Number of units purchased
- **InvoiceDate**: Date of purchase
- **UnitPrice**: Price per unit
- **CustomerID**: Unique customer identifier
- **Country**: Country of purchase

## Key Steps
### 1. Data Preprocessing
- Load the dataset using `pandas`.
- Handle missing values by filtering out rows with missing `CustomerID`.
- Filter for positive `Quantity` values to remove returns.
- Create a `Sales` column by multiplying `Quantity` and `UnitPrice`.
- Select relevant columns: `CustomerID`, `InvoiceDate`, and `Sales`.

### 2. Customer Behavior Summary
- Compute **frequency**, **recency**, **tenure (T)**, and **monetary value** using the `lifetimes` package.
- Visualize customer purchasing frequency using histograms.

### 3. BG/NBD Model for Purchase Predictions
- Fit a **Beta-Geometric/NBD (BG/NBD)** model to predict customer purchase probability.
- Generate a **Frequency-Recency Matrix** to analyze customer segments.
- Plot the **Probability Alive Matrix** to identify valuable customers.

### 4. Predicting Future Purchases
- Estimate the number of purchases a customer is expected to make in the next period (`t=1, 10` days).
- Validate predictions by comparing calibration and holdout periods.
- Visualize purchase predictions against actual transactions.

### 5. Gamma-Gamma Model for Revenue Prediction
- Fit a **Gamma-Gamma** model to estimate average customer spending.
- Compute **Customer Lifetime Value (CLV)** based on predicted purchases and spending.

## Dependencies
Ensure you have the following Python libraries installed:
```sh
pip install pandas seaborn matplotlib lifetimes openpyxl
```

## Running the Project
1. Place the dataset (`Online_Retail.xlsx`) inside the `./input_data/` folder.
2. Run the script:
```sh
python customer_lifetime_analysis.py
```
3. The script outputs:
   - Processed customer behavior summary
   - Visualizations of purchase frequency and revenue
   - Predicted purchases and estimated customer lifetime value

## Results
- The model provides insights into customer purchase patterns.
- High-frequency customers are predicted to make more purchases in the future.
- The Gamma-Gamma model estimates the potential revenue contribution per customer.

## Future Improvements
- Expand to other datasets for different industries.
- Tune model parameters for improved accuracy.
- Integrate real-time data pipelines for dynamic predictions.


