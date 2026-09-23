# Retail Sales Analysis Project

A complete Python-based Data Analytics project that cleans, analyzes, and visualizes 1,500 retail sales transactions across 8 cities to uncover business insights on revenue, product performance, discounting, and customer behavior.

---

## 🎓 Internship Details

**AICTE | IBM SkillsBuild Data Analytics with AI Internship 2026**  
Conducted by **BharatCares** in association with **AICTE**

---
## 📌 Project Overview

Retail businesses generate large volumes of transactional data that, left unanalyzed, offer little strategic value. This project takes raw retail sales data and turns it into structured business intelligence.

- **What it is:** An end-to-end data analysis of retail sales transactions using Python.
- **Problem it solves:** A retail company needed to understand its sales performance, customer behavior, product performance, discount impact, and payment trends to support management decision-making.
- **Why it matters:** Understanding these patterns helps a retail business prioritize marketing spend, plan inventory and staffing around demand cycles, evaluate whether discounting is actually growing revenue, and identify top- and under-performing products, cities, and salespeople.
- **What was analyzed:** 1,500 sales orders placed across 8 Maharashtra cities over an 18-month period (January 2025 – June 2026), covering products, categories, pricing, discounts, payment methods, customer types, and salespersons.

---

## 🎯 Objectives

- Load and validate the retail sales dataset using Pandas.
- Explore the dataset's structure, data types, and statistical distribution.
- Identify and handle missing values, and check for duplicate records.
- Convert the `Date` column into a proper datetime type.
- Perform numerical analysis (total, average, min, max sales) using NumPy.
- Analyze sales by city, category, product, salesperson, and customer type.
- Analyze sales by month, quarter, and year.
- Perform filtering and sorting on the dataset.
- Create visualizations using Matplotlib and Seaborn.
- Analyze correlations between numerical variables, including the effect of discounting.
- Extract and document meaningful business insights and recommendations.

---

## 📊 Dataset

| Detail | Value |
|---|---|
| **File** | `retail_sales_analysis_project.csv` |
| **Rows** | 1,500 |
| **Columns** | 18 |
| **Time period covered** | January 2025 – June 2026 (18 months) |
| **Cities covered** | Nashik, Thane, Kolhapur, Navi Mumbai, Pune, Aurangabad, Nagpur, Mumbai |
| **Categories covered** | Electronics, Furniture, Sports, Clothing, Beauty, Grocery |

**Column reference:**

| Column | Description | Data Type |
|---|---|---|
| `Order_ID` | Unique order number | int64 |
| `Date` | Date of order | object → datetime64 (after cleaning) |
| `City` | Order city | object |
| `Category` | Product category | object |
| `Product` | Product name | object |
| `Quantity` | Units sold | int64 |
| `Unit_Price` | Price per unit | float64 |
| `Discount_Percent` | Discount given (%) | float64 |
| `Payment_Method` | Payment type used | object |
| `Customer_Type` | New, Returning, or VIP | object |
| `Salesperson` | Employee handling the sale | object |
| `Gross_Sales` | Sales value before discount | float64 |
| `Discount_Amount` | Value of discount applied | float64 |
| `Net_Sales` | Final sales value after discount | float64 |
| `Month` | Month name of order | object |
| `Month_Number` | Numeric month (1–12) | int64 |
| `Quarter` | Quarter of order (Q1–Q4) | object |
| `Year` | Year of order | int64 |

> Dataset source: provided as part of the project brief; no external data was used.

---

## 🛠️ Technologies & Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## 🔄 Project Workflow

```
Data Loading
   ↓
Data Exploration
   ↓
Data Cleaning
   ↓
Date/Type Conversion
   ↓
Numerical Analysis (NumPy)
   ↓
Exploratory Data Analysis (Pandas)
   ↓
Visualization (Matplotlib & Seaborn)
   ↓
Business Insights
   ↓
Recommendations
```

---

## 🧹 Data Cleaning

| Step | Before | Action | After |
|---|---|---|---|
| Missing values | 39 missing values (2.6% of all cells): `Discount_Percent` (15), `Payment_Method` (12), `Customer_Type` (12) | Filled `Discount_Percent` with the column **median**; filled `Payment_Method` and `Customer_Type` with the column **mode** | 0 missing values across all 18 columns |
| Duplicate records | `df.duplicated().sum()` → 0 duplicates found | `df.drop_duplicates()` applied as a safeguard | Row count unchanged at 1,500 |
| Date type | `Date` stored as `object` (text) | `pd.to_datetime(df["Date"])` applied | `Date` dtype converted to `datetime64[ns]` |

Final cleaned dataset shape: **(1,500, 18)**.

---

## 🔍 Exploratory Data Analysis

- **Numerical analysis (NumPy):** total, average, minimum, and maximum Net Sales.
- **Group-wise sales analysis:** by City, Category, Product, Salesperson, and Customer Type.
- **Time-based analysis:** sales aggregated by Month, Quarter, and Year.
- **Filtering & sorting:** orders with Net Sales above ₹50,000; highest- and lowest-value orders.
- **Discount analysis:** average Net Sales by discount tier, and correlation between `Discount_Percent` and `Net_Sales`.
- **Correlation analysis:** full correlation matrix across all numeric columns.
- **Business-question analysis:** 12 specific business questions (top city, top product, top category, top salesperson, most popular payment method, etc.) answered directly from the data.

---

## 📈 Data Visualization

All charts below were generated with Matplotlib/Seaborn and are the actual outputs saved in the project notebook.

| # | Visualization | Type | What It Shows |
|---|---|---|---|
| 1 | City-wise Sales | Bar Chart | Total Net Sales ranked across all 8 cities |
| 2 | Monthly Sales Trend | Line Chart | Total Net Sales by month, revealing seasonal patterns |
| 3 | Quantity vs Net Sales | Scatter Plot | Relationship between units sold and sales value |
| 4 | Net Sales Distribution | Histogram | Spread of individual order values |
| 5 | Payment Method Distribution | Pie Chart | Share of orders by payment method |
| 6 | Category-wise Orders | Count Plot | Number of orders placed per category |
| 7 | Category-wise Sales | Bar Plot | Total Net Sales per category |
| 8 | Sales Distribution by Category | Box Plot | Spread and outliers of order values within each category |
| 9 | Quantity vs Net Sales by Category | Scatter Plot (hue) | Quantity–sales relationship, split by category |
| 10 | Correlation Heatmap | Heatmap | Correlation strength across all numeric columns |
| 11 | Pair Plot | Pair Plot | Pairwise relationships between Quantity, Unit Price, and Net Sales |

---

## 💡 Key Insights

1. **Nashik** generates the highest revenue (₹73.69 lakh) among all 8 cities, while **Mumbai** generates the least (₹47.76 lakh).
2. **Electronics** is the dominant category, contributing ₹3.13 crore of total Net Sales — more than the next four categories combined.
3. **Unit Price** is the strongest driver of a sale's value (correlation **0.87** with Net Sales), far outweighing Quantity (correlation **0.24**).
4. **Discount level has almost no relationship with Net Sales** (correlation **-0.04**); 15% and 20% discount orders actually show *lower* average Net Sales than 0%, 5%, or 10% discount orders.
5. **Karan** is the top-performing salesperson (₹65.41 lakh in Net Sales) — nearly double the lowest performer, Vikas (₹33.15 lakh).
6. **UPI** is the most popular payment method among customers in this dataset.
7. **Returning customers** generate the most total revenue (₹2.28 crore), ahead of New (₹2.04 crore) and VIP (₹74.96 lakh) customers.
8. **January** is the highest-revenue month and **Q1** the highest-revenue quarter; revenue declines through Q3 before a partial Q4 recovery.
9. **Flour** is the best-selling product by quantity but ranks among the lowest by revenue — high sales volume does not always mean high revenue.
10. **Grocery items** (Sugar, Flour, Biscuits) dominate the lowest-value individual orders, consistent with Grocery being the lowest-revenue category overall.

---

## 📋 Business Recommendations

| Finding | Recommendation |
|---|---|
| Nashik and Electronics drive a disproportionate share of revenue | Prioritize marketing and inventory investment in these strong areas while investigating why Mumbai and Grocery underperform |
| 15%–20% discounts show *lower* average Net Sales, with near-zero overall correlation to sales | Re-evaluate whether discounts above 10% are actually necessary |
| Karan generates ~2x the sales of the lowest-performing salesperson | Study Karan's approach and share best practices with lower-performing staff |
| Returning customers are already the highest-value segment | Invest in loyalty/repeat-purchase programs targeted at this segment |
| Sales peak in Q1 and dip in Q3 | Align inventory and staffing plans with this seasonal pattern |

---

## 📁 Project Structure

```
IBM-SkillsBuild-Retail-Sales-Analysis/
├── README.md
├── requirements.txt
├── MaheshChaudhari_RetailSalesAnalysis.ipynb
├── MaheshChaudhari_ProjectReport.docx
└── cleaned_retail_sales_data.csv
```
## 🚀 How to Run the Project

1. **Clone the repository**
   ```bash
   git clone https://github.com/MaheshChaudhari7/IBM-SkillsBuild-Retail-Sales-Analysis.git
   ```
2. **Navigate to the project folder**
   ```bash
   cd Retail-Sales-Analysis
   ```
3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
4. **Run the notebook**
   ```bash
   jupyter notebook notebooks/RETAIL_SALES_ANALYSIS_PROJECT_ipynb_code.ipynb
   ```
   Run all cells in order. Ensure `retail_sales_analysis_project.csv` is in the `data/` folder (or update the file path in the first code cell).

---

## 📦 Requirements

```
pandas
numpy
matplotlib
seaborn
jupyter
```

---

## 📊 Results

The analysis processed 1,500 transactions into a fully cleaned dataset (0 missing values, 0 duplicates), computed total Net Sales of ₹5.09 crore (average ₹33,946.44 per order), answered all 12 business questions from the problem statement, and produced 11 visualizations covering distribution, comparison, trend, and correlation analysis. The findings point to Unit Price — not order quantity or discount level — as the primary driver of sales value in this dataset.

---

## 🔮 Future Scope

*The following are proposed future improvements and are **not** part of the current implementation:*

- Power BI / Tableau dashboard for interactive exploration
- Automated monthly/quarterly reporting
- Sales forecasting using time-series models
- Customer segmentation (e.g., RFM analysis)
- Predictive analytics / ML models for order value or discount sensitivity
- Real-time analytics on a live transactional feed

---

## 📄 Project Report

📄 [View / Download Project Report](https://github.com/MaheshChaudhari7/Retail-Sales-Analysis/blob/main/Retail-Sales-Analysis-Report.docx)

---

## 👤 Author

**Mahesh Chaudhari**

- Aspiring Data Analyst
- Passionate about turning data into business insights

**Connect with me:**
- LinkedIn: [Mahesh Chaudhari](https://www.linkedin.com/in/mahesh-chaudhari-5856332a1)
- GitHub: [MaheshChaudhari7](https://github.com/MaheshChaudhari7)
- Email: mahesh.chaudhari.ds@gmail.com
