# Retail Market Basket Analysis

This project explores **data mining techniques** using a real-world **UK-based online retail dataset**. The goal is to uncover meaningful patterns and insights from customer transactions, with a special focus on **association discovery** (market basket analysis).

---

##  Dataset Overview

The dataset includes **541,909 transaction records** between **December 1, 2010** and **December 1, 2011**, describing online purchases from a UK-based retailer.

###  Features:

| Column       | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| `InvoiceNo`  | Unique invoice number. Shared across rows if part of the same order.        |
| `StockCode`  | Product identifier (alphanumeric).                                          |
| `Description`| Product name in uppercase.                                                  |
| `Quantity`   | Number of items purchased in the transaction.                              |
| `InvoiceDate`| Timestamp of the transaction (dd/mm/yyyy h:m).                              |
| `UnitPrice`  | Price per unit in euros.                                                    |
| `CustomerID` | Unique customer identifier.                                                 |
| `Country`    | Country of the customer.                                                    |

---

##  Data Preprocessing

We performed several cleaning steps to ensure data quality:

###  Summary of Cleaning Steps:

| Step                                   | Remaining Rows |
|----------------------------------------|----------------|
| Original Dataset                       | 541,909        |
| After Removing Duplicates              | 541,909        |
| After Removing Negative Unit Prices    | 541,907        |
| After Removing Negative Quantities     | 531,283        |
| After Removing Null `CustomerID`       | 397,924        |
| After Removing Null `Description`      | 397,924        |

- **Final dataset size:** 397,924 rows  
- Negative `Quantity` values were associated with **canceled transactions** (e.g., InvoiceNo starting with "C").

---

##  Data Analysis & Visualization

Key analysis dimensions:

###  Geographic Insights
- Identified the **top countries** by transaction volume.
- Helped highlight where most customers are located.

###  Best-Selling Products
- Generated a list of **top 10 selling products**.
- Useful to identify high-demand items, though may need further refinement for profitability analysis.

###  Temporal Trends
- **Monthly breakdown** of sales reveals peak purchase times.
- Helps with **logistics planning** and stock forecasting.

---

##  Association Discovery (Market Basket Analysis)

We used **association rule mining** to identify products that are frequently bought together.

###  Why Association Rules?
- Helps detect **buying patterns**.
- Useful for **product placement**, **recommendations**, **bundles**, and **targeted promotions**.

###  Metrics Explained

- **Support:** Frequency of itemset in the dataset.
- **Confidence:** Likelihood of consequent given the antecedent.
- **Lift:** Strength of association.  
  - `>1`: Positive association  
  - `=1`: No association  
  - `<1`: Negative association

###  Algorithm Used

We used the **Apriori algorithm** to generate:
- Frequent itemsets
- Association rules

### 📈 Example Association Rules

- `If A → then B` (high confidence, high lift)
- Extended to **three-way associations** like:  
  `If A and B → then C`

These deeper patterns allow for **greater granularity** and richer insights.

---

##  Applications of Association Rules

- **Product Placement**: Group strongly associated items in stores.
- **Online Recommendations**: "Customers also bought" suggestions.
- **Targeted Advertising**: Promote associated products to past buyers.
- **Conditional Promotions**: Discounts when products are bought together.
- **Bundling**: Sell associated products as a single package.

---

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