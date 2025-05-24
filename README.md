# 🧩 Customer Segmentation using K-Means Clustering  
### 📦 Snapdeal Menternship Project

Welcome to the repository of my Data Science project from the Snapdeal Menternship Program.
This project focuses on identifying distinct customer segments using K-Means Clustering. By analyzing purchasing behavior from the Online Retail dataset, the aim is to uncover key customer groups to enable more targeted and effective marketing strategies.



---

## 📌 Project Overview

Customer segmentation enables businesses like Snapdeal to:
- Understand diverse buying behaviors
- Tailor promotions and product recommendations
- Improve customer retention and engagement

This project uses **unsupervised machine learning** (K-Means) on real transactional data to group customers into meaningful segments.

---

## 🔁 Workflow

### Step 1: Load and Explore Dataset
- Dataset: `Online Retail.xlsx`
- Source: UK-based e-commerce transactions
- Performed EDA: missing values, data types, initial trends

### Step 2: 🧹 Data Cleaning
- Removed rows with missing `CustomerID` or `Description`
- Filtered out cancelled and invalid transactions
- Excluded negative or zero values in `Quantity` and `UnitPrice`

### Step 3: 🏗️ Feature Engineering
- Calculated `TotalSpent = Quantity × UnitPrice`
- Aggregated features per customer:
  - Number of Orders
  - Total Quantity Purchased
  - Total Amount Spent
  - Recency (days since last purchase)

### Step 4: ⚙️ Feature Preparation
- Selected features for clustering: `NumOrders`, `TotalQuantity`, `TotalSpent`, `Recency`
- Standardized features using `StandardScaler`

### Step 5: 🔎 Optimal Clusters
- Applied the **Elbow Method** using Within-Cluster Sum of Squares (WCSS)
- Determined optimal `k = 4`

### Step 6: 🔀 Run K-Means
- Performed KMeans clustering with `k = 4`
- Assigned cluster labels to each customer

### Step 7: 🖼️ Visualize Clusters
- Reduced dimensions via **PCA**
- Visualized customer clusters using:
  - PCA-based scatter plots
  - Cluster distribution count plots

### Step 8: 🧠 Interpret Clusters

| Cluster | Segment Name               | Description                                      | Suggested Strategy                              |
|---------|----------------------------|--------------------------------------------------|--------------------------------------------------|
| 0       | Mid-Tier Customers         | Moderate spend and frequency                     | Loyalty programs, regular engagement             |
| 1       | Inactive/Churned Customers | Low spend and recent inactivity                  | Reactivation via emails or limited-time offers   |
| 2       | Loyal High-Value Customers | High spend, high frequency, recent activity      | Personalized offers, VIP loyalty perks           |
| 3       | Wholesale/Top Buyers       | Bulk orders and high total spend                 | Dedicated account support, wholesale pricing     |

---

## 📈 Results & Business Recommendations

### 📊 Summary of Insights
- Customers are **not homogenous** — behaviors vary significantly across segments.
- A small portion of customers (Cluster 2) contribute disproportionately to revenue.
- A large group (Cluster 1) shows signs of **churn risk** and requires re-engagement.

### 💼 Recommended Actions
- **Cluster 2 (Loyal VIPs):** Reward loyalty with exclusive deals or early access
- **Cluster 3 (Wholesale Buyers):** Offer bulk discounts and a dedicated account manager
- **Cluster 1 (Churned Users):** Launch win-back campaigns with personalized emails
- **Cluster 0 (Mid-Tier):** Encourage upsell/cross-sell via customized recommendations

---
