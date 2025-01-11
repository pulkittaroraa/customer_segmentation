# Customer Segmentation with K-Means Clustering

This project applies K-Means clustering to perform customer segmentation for a business, helping to better understand its customer base and uncover valuable insights. The project includes exploratory data analysis (EDA), preprocessing, feature engineering, and the clustering pipeline.

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Methodology](#methodology)
   - Data Cleaning
   - Feature Engineering
   - K-Means Clustering
4. [Results](#results)
5. [How to Use](#how-to-use)
6. [Conclusion](#conclusion)

---

## Introduction
Customer segmentation helps businesses understand distinct groups within their customer base, allowing targeted marketing, personalized recommendations, and strategic decision-making. This project demonstrates the use of the K-Means algorithm to cluster customers based on their transactional behavior.

---

## Dataset
The dataset used in this project is a transactional dataset containing the following columns:
- **Invoice**: Unique invoice identifier.
- **StockCode**: Product code.
- **Description**: Product description.
- **Quantity**: Number of units sold.
- **InvoiceDate**: Date and time of the transaction.
- **Price**: Unit price of the product.
- **Customer ID**: Unique customer identifier (may contain missing values).
- **Country**: Country of the customer.

**Dataset Size**: 525,461 rows and 8 columns.

---

## Methodology

### 1. Data Cleaning
- **Invoice Filtering**: Removed non-standard invoices (e.g., non-numeric or invalid formats).
- **Handling Missing Data**: 
  - Addressed missing `Description` and `Customer ID` values through imputation or exclusion.
- **Negative Values**: Inspected and handled negative `Quantity` and `Price` values, likely representing returns or errors.

### 2. Feature Engineering
- Created meaningful features such as:
  - **Total Spend**: Computed as `Quantity * Price`.
  - **Recency**: Time difference from the most recent purchase.
  - **Frequency**: Number of purchases by a customer.
  - **Monetary Value**: Total spend by a customer.
- Standardized features for clustering using `StandardScaler`.

### 3. K-Means Clustering
- **Optimal Number of Clusters**:
  - Evaluated using the Elbow Method (Inertia).
  - Validated using Silhouette Scores.
- **Implementation**:
  - Performed clustering using the `KMeans` algorithm with the optimal `k`.
  - Visualized cluster distributions and characteristics.

---

## Results
- Identified distinct customer segments based on purchasing patterns, recency, and spend.
- Visualized cluster insights through:
  - Spending behavior.
  - Product preferences.
  - Geographic distribution of customers.

---

## How to Use

### Prerequisites
- Python 3.x
- Libraries: `pandas`, `matplotlib`, `seaborn`, `scikit-learn`

### Steps
1. Clone the repository and download the dataset.
2. Install dependencies: `pip install -r requirements.txt`.
3. Run the Jupyter notebook `customer_segmentation.ipynb`.
4. Modify parameters as needed (e.g., clustering `k`, scaling options).

---

## Conclusion
This project demonstrates the potential of clustering for customer segmentation. The insights derived can help businesses tailor strategies to maximize customer satisfaction and profitability.
