# 🛍️ Customer Shopping Behavior Analysis

A full-stack data analysis project exploring retail customer behavior through Python, MySQL, and Power BI — covering data cleaning, feature engineering, SQL querying, and interactive dashboard visualization.

---

## 📁 Project Structure

```
├── customer_shopping_behavior.csv        # Raw dataset (3,900 customer records)
├── Customer_Shopping_Behavior_Analysis.ipynb  # Data cleaning, EDA & pipeline notebook
├── Customer_Behavior.sql                 # Business intelligence SQL queries
└── customer_behavior_dashboard.pbix      # Power BI interactive dashboard
```

---

## 📊 Dataset Overview

| Feature | Details |
|---|---|
| Records | 3,900 customers |
| Columns | 18 (Age, Gender, Category, Purchase Amount, Review Rating, etc.) |
| Source | Retail shopping transaction data |

**Key Columns:** `Customer ID`, `Age`, `Gender`, `Item Purchased`, `Category`, `Purchase Amount (USD)`, `Review Rating`, `Subscription Status`, `Shipping Type`, `Discount Applied`, `Previous Purchases`, `Frequency of Purchases`

---

## 🐍 Python Analysis (Jupyter Notebook)

### Data Cleaning
- Imputed missing `Review Rating` values using **category-wise median**
- Standardized column names to **snake_case** for consistency
- Dropped redundant `Promo Code Used` column (100% correlated with `Discount Applied`)

### Feature Engineering
- **`age_group`** — Quartile-based segmentation: `Young Adult`, `Adult`, `Middle-aged`, `Senior`
- **`purchase_frequency_days`** — Mapped frequency labels (Weekly → 7, Monthly → 30, etc.) to numeric values

### Data Pipeline
- Loaded cleaned DataFrame into a **MySQL database** using `SQLAlchemy` + `PyMySQL`
- Schema: single `customer` table in `customer_behavior` database

---

## 🗄️ SQL Analysis

10 business intelligence queries covering:

| # | Question |
|---|---|
| Q1 | Total revenue by gender |
| Q2 | Discount users who spent above average |
| Q3 | Top 5 products by average review rating |
| Q4 | Average purchase amount: Standard vs Express shipping |
| Q5 | Subscriber vs non-subscriber spend comparison |
| Q6 | Top 5 products by discount usage rate |
| Q7 | Customer segmentation — New / Returning / Loyal |
| Q8 | Top 3 products per category (Window Functions) |
| Q9 | Repeat buyers (>5 purchases) vs subscription status |
| Q10 | Revenue contribution by age group |

**SQL Concepts Used:** `CTEs`, `Window Functions (ROW_NUMBER, PARTITION BY)`, `Subqueries`, `CASE`, `GROUP BY`, `ROUND`, `Aggregations`

---

## 📈 Power BI Dashboard

Interactive dashboard (`customer_behavior_dashboard.pbix`) visualizing:
- Revenue breakdown by gender and age group
- Product category performance
- Shipping preference trends
- Discount and subscription impact on spending

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python (Pandas) | Data cleaning & feature engineering |
| Jupyter Notebook | Exploratory data analysis |
| MySQL | Relational database & SQL querying |
| SQLAlchemy + PyMySQL | Python-to-MySQL data pipeline |
| Power BI | Interactive dashboard & visualization |

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/customer-shopping-behavior.git
cd customer-shopping-behavior
```

### 2. Install Python Dependencies
```bash
pip install pandas sqlalchemy pymysql jupyter
```

### 3. Run the Notebook
```bash
jupyter notebook Customer_Shopping_Behavior_Analysis.ipynb
```

### 4. Set Up MySQL
```sql
CREATE DATABASE customer_behavior;
```
Update the database credentials in the notebook before running the pipeline cell.

### 5. Run SQL Queries
Open `Customer_Behavior.sql` in MySQL Workbench or any SQL client and execute queries against the `customer_behavior` database.

### 6. Open Power BI Dashboard
Open `customer_behavior_dashboard.pbix` in **Power BI Desktop** and refresh the data source connection.

---

## 💡 Key Insights

- Subscribed customers show **higher average spend** and contribute disproportionately to total revenue
- Certain product categories have **significantly higher discount rates**, impacting margin
- **Loyal customers** (10+ purchases) are more likely to hold active subscriptions
- Revenue distribution varies meaningfully across **age groups and genders**

---

## 📄 License

This project is for educational and portfolio purposes.
