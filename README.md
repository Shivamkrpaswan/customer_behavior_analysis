# Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores customer shopping behavior using Python, SQL, and Power BI — covering data cleaning, exploratory analysis, business-question querying, and interactive dashboarding.

---

## Overview

This project analyzes transactional shopping data to uncover patterns in customer spending, product preferences, and subscription behavior. The workflow moves through the full analytics pipeline: data cleaning in Python, structured business analysis in SQL, and visualization in Power BI — concluding with a summary report and presentation of key findings.

**Goal:** Turn raw transaction data into actionable insights that support marketing, retention, and product decisions.

---

## Dataset

- **Size:** 3,900 rows × 18 columns
- **Contents:**
  - Customer demographics — Age, Gender, Location, Subscription Status
  - Purchase details — Item Purchased, Category, Purchase Amount, Season, Size, Color
  - Shopping behavior — Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type
- **Data quality:** 37 missing values in the Review Rating column, handled during cleaning

---

## Tools & Technologies

| Category | Tools |
|---|---|
| Data Handling & EDA | Python (pandas) |
| Database / Querying | PostgreSQL |
| Visualization | Power BI |
| Reporting | Word / PDF |
| Presentation | Gamma |

---

## Steps

**1. Data Loading & Cleaning (Python)**
- Loaded the dataset with pandas; inspected structure using `df.info()` and `.describe()`
- Identified and imputed missing Review Rating values using the median rating per product category
- Standardized column names to snake_case
- Engineered new features: `age_group` (binned ages) and `purchase_frequency_days`
- Checked for redundant columns (e.g., dropped `promo_code_used` after confirming overlap with `discount_applied`)

**2. Database Integration**
- Connected the cleaned dataset to a SQL database (PostgreSQL / MySQL / SQL Server) for structured querying

**3. SQL Analysis**
Answered key business questions using SQL, including:
- Revenue by gender
- High-spending customers who still used discounts
- Top-rated products
- Shipping type comparison (Standard vs. Express)
- Subscriber vs. non-subscriber spending
- Discount-dependent products
- Customer segmentation (New, Returning, Loyal)
- Top products per category
- Repeat buyer and subscription correlation
- Revenue by age group

**4. Dashboard (Power BI)**
- Built an interactive dashboard with filters for subscription status, gender, category, and shipping type
- Visualized KPIs, revenue and sales by category, and revenue/sales by age group

**5. Reporting & Presentation**
- Compiled findings into a written report
- Created a summary presentation using Gamma for stakeholder-friendly delivery

---

## Dashboard

The Power BI dashboard includes:
- **KPIs:** Total customers, average purchase amount, average review rating
- **Filters:** Subscription status, gender, category, shipping type
- **Visuals:** Customer split by subscription status, revenue and sales by category, revenue and sales by age group

*(Add a screenshot or link to the published dashboard here.)*

---

## Results

- Male customers generated significantly higher total revenue than female customers
- Young Adults contributed the highest revenue among age groups, though the gap across groups was narrow
- Non-subscribers accounted for the majority of both customers and revenue
- Certain products (Hat, Sneakers, Coat) showed a high dependency on discounts to drive sales
- Most customers fell into the "Loyal" segment, indicating strong repeat purchase behavior

**Business Recommendations:**
- Boost subscriptions through exclusive member benefits
- Introduce loyalty programs to convert returning customers into loyal ones
- Reassess discount-heavy products to protect margins
- Prioritize top-rated, best-selling products in marketing campaigns
- Target high-revenue age groups and express-shipping users in campaigns

---

## How to Run

1. **Clone the repository**
   ```bash
   git clone <repo-url>
   cd customer-shopping-behavior-analysis
   ```

2. **Set up the Python environment**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the EDA & cleaning script**
   ```bash
   python eda_cleaning.py
   ```

4. **Load data into your SQL database**
   - Update database credentials in the config file
   - Run the load script to push the cleaned dataset into PostgreSQL / MySQL / SQL Server

5. **Run SQL queries**
   - Execute the `.sql` files in the `/sql` folder against your database

6. **Open the dashboard**
   - Open `dashboard.pbix` in Power BI Desktop to explore the visuals

7. **View the report and presentation**
   - Report: `/report/Customer_Shopping_Behavior_Analysis.docx`
   - Presentation: link to Gamma deck

---

## Project Structure

```
├── data/
│   └── shopping_behavior.csv
├── eda_cleaning.py
├── sql/
│   ├── revenue_by_gender.sql
│   ├── customer_segmentation.sql
│   └── ...
├── dashboard.pbix
├── report/
│   └── Customer_Shopping_Behavior_Analysis.docx
├── requirements.txt
└── README.md
```

---

## Author

Shivam — B.Tech student transitioning into data analytics.
