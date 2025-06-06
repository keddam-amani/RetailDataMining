# Retail Market Basket Analysis

## Overview

This project was conducted as part of a Knowledge Discovery and Data Mining course. Its main objective is to extract useful patterns from real-world retail transaction data by applying association rule mining techniques. The focus was placed on discovering meaningful associations between products, which can be used to support decision-making in areas such as recommendation systems, marketing, and inventory planning.

## Dataset Description

The dataset used in this project contains detailed transaction records from a UK-based online retail store. It includes purchases made between **December 1, 2010, and December 1, 2011**, with a total of **541,909 records** and **8 attributes**:

- `InvoiceNo`: Unique identifier for each transaction.
- `StockCode`: Unique product code.
- `Description`: Product name.
- `Quantity`: Number of items purchased.
- `InvoiceDate`: Timestamp of the transaction.
- `UnitPrice`: Price per item (in euros).
- `CustomerID`: Unique identifier for each customer.
- `Country`: Customer’s country.

## Data Preprocessing

To ensure accurate analysis, a thorough data cleaning process was applied:

- **Duplicate Records**: No duplicate rows were found.
- **Negative Values**: Transactions with negative `Quantity` or `UnitPrice` were removed. Negative quantities usually represented cancellations (invoices starting with "C").
- **Missing Values**: Entries with missing `CustomerID` and `Description` were dropped due to lack of reliable repair methods.

**Final dataset size**:  
After preprocessing, **397,924 rows** remained from the original **541,909**.

## Exploratory Analysis

A series of visualizations and basic analyses were performed:

- **Geospatial Analysis**: Countries with the most orders were identified.
- **Top-Selling Products**: Products with the highest total quantities sold were listed.
- **Time Series Analysis**: Monthly sales trends were plotted to highlight seasonal patterns and peak demand periods.

These insights are useful for understanding customer behavior and optimizing supply and logistics.

## Association Rule Mining

### Technique Used

The **Apriori algorithm** was applied to find frequent itemsets and generate association rules. This method is particularly effective in the retail domain for identifying items frequently purchased together.

### Metrics Used

- **Support**: Frequency of an itemset in the dataset.
- **Confidence**: Likelihood of seeing item B in a transaction that contains item A.
- **Lift**: Strength of the association; values >1 indicate a positive correlation.

### Rule Discovery

Rules of the form:
```
If Product A is bought → Product B is likely to be bought
```
were generated and evaluated using the above metrics. Additionally, **three-item association rules** were analyzed to find deeper patterns.

### Applications

The resulting rules can be used in:

1. **Online Recommendations** – Suggesting products to users during browsing or checkout.
2. **Targeted Advertising** – Promoting products that customers are likely to buy together.
3. **Promotional Campaigns** – Creating bundle offers or conditional discounts.
4. **In-store Layout Optimization** – Placing related items close to each other.

## Limitations and Suggestions for Improvement

- The dataset did not include product costs, so only revenue (not profit) could be analyzed.
- More advanced techniques such as **clustering** could be used to predict user behavior or enrich the understanding of customer groups.

## Conclusion

This project successfully demonstrated how data mining techniques such as association rule mining can reveal actionable insights in a retail setting. The findings have practical implications for improving customer experience, increasing sales, and supporting strategic business decisions.


##  Tools & Technologies

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- `mlxtend` (for Apriori and association rules)

---
## How to Run

1. Create virtual env: 
    ```python3 -m venv myenv```

2. Activate your virtual environment.

3. Install required libraries in virtual environment:
    ```pip3 install -r requirements.txt```
