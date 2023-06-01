# Retail Market Basket Analysis

This project applies data mining techniques to retail transaction data to uncover product purchase patterns using association rule mining (Apriori algorithm). The analysis focuses on exploring customer behavior, product affinities, and sales trends.

---

## Dataset

The dataset consists of **online retail transactions**, including:
- Invoice number
- Stock code
- Product description
- Quantity
- Invoice date
- Unit price
- Customer ID
- Country

> **Note:** Data was cleaned to remove missing and invalid entries (e.g., negative quantities/prices, null Customer IDs).

---

## Objectives

- Perform data cleaning and preprocessing
- Visualize purchase behavior over time
- Use association rule mining to find product affinities
- Identify best-selling products and sales trends by country and hour

---

## Methods Used

- **Pandas, NumPy** – Data manipulation and cleaning  
- **Matplotlib, Seaborn** – Data visualization  
- **MLxtend, Apyori** – Association rule mining (Apriori algorithm)  
- **Excel, OpenPyXL** – Data import/export  

## How to Run

1. Install required libraries:
```bash
pip install pandas matplotlib seaborn openpyxl mlxtend apyori