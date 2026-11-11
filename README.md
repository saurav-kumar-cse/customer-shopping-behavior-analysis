# 🛍️ Customer Shopping Behavior Analysis

An end-to-end data analytics project that uses **Python, MySQL and Power BI** to uncover how customers shop, what drives their purchase decisions, and how a retail business can improve engagement, loyalty and marketing ROI.

---

## 📌 Table of Contents
- [Business Problem](#-business-problem)
- [Project Objectives](#-project-objectives)
- [Dataset Overview](#-dataset-overview)
- [Tech Stack](#-tech-stack)
- [Project Workflow](#-project-workflow)
- [Key Insights](#-key-insights)
- [Dashboard](#-dashboard)
- [Business Recommendations](#-business-recommendations)
- [Repository Structure](#-repository-structure)
- [How to Run](#-how-to-run)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

---

## 🎯 Business Problem

A leading retail company has noticed shifting purchasing patterns across demographics, product categories and sales channels (online vs. offline). Management wants to know which factors — **discounts, reviews, seasons, payment preferences** — drive consumer decisions and repeat purchases.

> **Key question:** *How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?*

## ✅ Project Objectives

1. **Data Preparation & Modeling (Python)** – clean and transform the raw dataset.
2. **Data Analysis (SQL)** – structure the data, simulate business transactions and extract insights on customer segments, loyalty and purchase drivers.
3. **Visualization & Insights (Power BI)** – build an interactive dashboard for stakeholders.
4. **Report & Presentation** – summarize findings and actionable recommendations.
5. **GitHub Repository** – well-organized Python scripts, SQL queries and dashboard files.

## 📊 Dataset Overview

| Property | Details |
|---|---|
| Rows | 3,900 purchase records |
| Columns | 18 |
| Missing values | 37 in `Review Rating` |

**Feature groups**
- **Customer demographics:** Customer ID, Age, Gender, Location, Subscription Status
- **Purchase details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
- **Shopping behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type, Payment Method

## 🧰 Tech Stack

| Purpose | Tools |
|---|---|
| Data cleaning & feature engineering | Python (pandas) |
| Database & analysis | MySQL |
| Visualization | Power BI |
| Version control | Git & GitHub |

## 🔄 Project Workflow

### 1. Data Preparation (Python)
- Loaded the dataset with `pandas` and inspected it using `df.info()` and `.describe()`.
- **Missing values:** imputed `Review Rating` with the **median rating of each product category**.
- **Standardization:** renamed all columns to `snake_case`.
- **Feature engineering:**
  - `age_group` – customer ages binned into groups (Young Adult, Adult, Middle-aged, Senior).
  - `purchase_frequency_days` – numeric version of purchase frequency.
- **Consistency check:** found `discount_applied` and `promo_code_used` redundant and dropped `promo_code_used`.
- **Database integration:** connected Python to MySQL and loaded the cleaned DataFrame for SQL analysis.

### 2. Data Analysis (SQL)
Ten business questions were answered with SQL:

| # | Analysis | Goal |
|---|---|---|
| 1 | Revenue by Gender | Compare male vs. female revenue |
| 2 | High-Spending Discount Users | Customers who used discounts but spent above average |
| 3 | Top 5 Products by Rating | Highest average review ratings |
| 4 | Shipping Type Comparison | Standard vs. Express average spend |
| 5 | Subscribers vs. Non-Subscribers | Average spend and total revenue |
| 6 | Discount-Dependent Products | Top 5 products by discounted-purchase share |
| 7 | Customer Segmentation | New, Returning and Loyal customers |
| 8 | Top 3 Products per Category | Best sellers within each category |
| 9 | Repeat Buyers & Subscriptions | Are customers with >5 purchases more likely to subscribe? |
| 10 | Revenue by Age Group | Revenue contribution per age segment |

### 3. Visualization (Power BI)
An interactive **Customer Behavior Dashboard** with filters for subscription status, gender, category and shipping type.

## 🔍 Key Insights

**Revenue & customers**
- **Male customers** generated about **$157.9K** in revenue versus about **$75.2K** from female customers.
- **Young Adults** contribute the most revenue (~$62.1K), followed by Middle-aged (~$59.2K), Adult (~$56.0K) and Senior (~$55.8K) — revenue is fairly evenly spread across age groups.
- Average purchase amount is **$59.76** and average review rating is **3.75**.

**Subscriptions**
- Only **27%** of customers (1,053) are subscribers, versus 73% (2,847) non-subscribers.
- Average spend is almost identical (**$59.49** subscribers vs. **$59.87** non-subscribers), so subscribers are not yet spending more per purchase.
- Non-subscribers account for most of the revenue (~$170.4K vs. ~$62.6K).

**Products & discounts**
- **Top-rated products:** Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78).
- **Most discount-dependent products:** Hat (50.00%), Sneakers (49.66%), Coat (49.07%), Sweater (48.17%), Pants (47.37%).
- **Clothing** and **Accessories** lead in both revenue and sales volume; Footwear and Outerwear trail.
- **839** customers used a discount and still spent above the average purchase amount.

**Shipping & loyalty**
- **Express** shipping has a slightly higher average spend ($60.48) than **Standard** ($58.46).
- Customer segments: **Loyal – 3,116**, **Returning – 701**, **New – 83** — the base is dominated by repeat customers.

## 📈 Dashboard

The Power BI dashboard includes:
- **KPIs:** Number of customers (3.9K), average purchase amount ($59.76), average review rating (3.75)
- Customers by subscription status (donut chart)
- Revenue and sales by category
- Revenue and sales by age group
- Slicers: subscription status, gender, category, shipping type
 

## 💡 Business Recommendations

1. **Boost subscriptions** – promote exclusive subscriber benefits (early access, free shipping, member pricing) so subscribers deliver higher value.
2. **Customer loyalty programs** – reward repeat buyers and move "Returning" customers into the "Loyal" segment.
3. **Review discount policy** – several products have discount rates near 50%; balance sales boosts with margin control.
4. **Product positioning** – feature top-rated and best-selling products in campaigns.
5. **Targeted marketing** – focus on high-revenue age groups and express-shipping users.

## 📁 Repository Structure
```
customer-shopping-behavior-analysis/
│
├── customer_shopping_behavior.csv      # raw dataset 
│
├
└── Customer_Shopping_Behavior_Analysis.ipynb                 # cleaning, feature engineering, MySQL load
│
└── customer_behavior_sql_queries.sql                # the 10 business analysis queries
│
└── customer_behavior_dashboard.pbix    # interactive dashboard
│
├── project_report.pdf
└── presentation.pptx
│
└── README.md
```

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/saurav-kumar-cse/customer-shopping-behavior-analysis.git
   cd customer-shopping-behavior-analysis
   ```
2. **Install dependencies**
   ```bash
   pip install pandas numpy sqlalchemy pymysql
   ```
3. **Run data preparation** – update your MySQL credentials in the script, then:
   ```bash
   python python/data_preparation.py
   ```
4. **Run SQL analysis** – open `customer_behavior_sql_queries.sql` in MySQL Workbench (or any MySQL client) and execute the queries against the loaded table.
5. **Open the dashboard** – open the `.pbix` file in Power BI Desktop and refresh the data source if needed.

## 🔮 Future Improvements
- Add RFM-based customer segmentation and clustering (K-Means).
- Build a churn / subscription-propensity prediction model.
- Analyze seasonality and payment-method effects in more depth.
- Automate the pipeline with scheduled refreshes.

## 👤 Author

**Saurav Kumar**
Aspiring Data Analyst | B.Tech CSE

- GitHub: [https://github.com/saurav-kumar-cse]
- LinkedIn: [https://www.linkedin.com/in/saurav-k-cse]

---

⭐ If you found this project helpful, consider giving it a star!