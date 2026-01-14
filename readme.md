# Adventure Works Sales Analytics – Power BI Project

*** Project Overview ***
This project is an end-to-end **Power BI Sales & Performance Analytics solution** built using the **AdventureWorks dataset**.  
The goal of the project is to analyze **sales, revenue, profit, orders, returns, customers, and geography** through interactive dashboards and advanced DAX measures.

The report consists of **4 main dashboards**, each focusing on a different business perspective:
- Executive Overview
- Geographic Analysis
- Product Performance
- Customer Analysis

---

##  Tools & Technologies
- **Power BI Desktop**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Excel (source data)**
- **GitHub (project documentation & version control)**

---

##  Dashboards Overview

1️⃣ Executive Dashboard
**Purpose:** High-level business performance tracking  

**Key KPIs:**
- Total Revenue
- Total Profit
- Total Orders
- Return Rate

**Insights Provided:**
- Revenue trend over time
- Orders by product category
- Monthly revenue, orders, and returns comparison
- Most ordered and most returned product types

**Key Measures Used:**
- Total Revenue  
- Total Profit  
- Total Orders  
- Return Rate  
- Previous Month Revenue / Orders / Profit  
- Target Revenue, Orders, and Profit  
- Revenue Target Gap, Order Target Gap, Profit Target Gap  

**Key Business Insights:**
1) Strong profitability with low returns:
The business generated $24.9M in revenue and $10.5M in profit, indicating healthy margins, while maintaining a low return rate of 2.2%, suggesting good product quality and customer satisfaction.

2) Sustained revenue growth over time:
Revenue shows a clear upward trend from 2020 to 2022, with recent months outperforming the trend line—signaling accelerating growth despite slight fluctuations in monthly orders.

2️⃣ Geographic (Map) Dashboard
**Purpose:** Analyze sales performance across regions  

**Features:**
- Interactive world map
- Region-based filtering (Europe, North America, Pacific)
- Country-level revenue distribution

**Insights Provided:**
- Top-performing regions and countries
- Regional contribution to overall revenue

**Key Measures Used:**
- Total Revenue  
- Total Orders  
- Total Customers  

**Key Business Insights:**
1) North America is the primary revenue driver:
The United States dominates sales, with Canada contributing moderately, making North America the most critical region for overall performance.

2) Strong presence across multiple global regions:
Europe (notably Germany, France, and the UK) and the Pacific region (Australia) show meaningful activity, highlighting diversified geographic demand beyond a single market.


---

3️⃣ Product Detail Dashboard
**Purpose:** Deep dive into product-level performance  

**Features:**
- Selected product analysis
- Monthly orders, revenue, and profit vs target
- Adjustable price parameter (What-if analysis)
- Return rate tracking

**Insights Provided:**
- Product profitability trends
- Impact of price adjustments on revenue and profit
- High-ticket and bulk orders analysis

**Key Measures Used:**
- Adjusted Price  
- Adjusted Revenue  
- Adjusted Profit  
- High Ticket Orders  
- Bulk Orders  
- Bike Sales, Bike Returns, Bike Return Rate  
- Monthly Revenue / Orders / Profit vs Target

**Key Business Insights:**
1) The 30 oz Water Bottle is the top-performing product, leading in both order volume and revenue, consistently meeting or closely tracking monthly targets.

2) Profit trends remain stable with minimal returns, indicating strong demand, healthy margins, and efficient product performance over time.
---

4️⃣ Customer Detail Dashboard
**Purpose:** Customer behavior and segmentation analysis  

**Features:**
- Unique customers count
- Revenue per customer
- Weekly customer trend
- Customer segmentation by income and occupation
- Top 100 customers by revenue

**Insights Provided:**
- High-value customers identification
- Revenue contribution per customer
- Customer growth trends

**Key Measures Used:**
- Total Customers  
- Average Revenue Per Customer  
- Full Name (Customer Detail)  
- Total Orders (Customer Detail)  
- Total Revenue (Customer Detail)  

**Key Business Insights:**
1) Customer base shows strong growth since mid-2021, with weekly customers rising steadily and peaking above 500, indicating successful acquisition momentum.

2) Revenue is concentrated among high-value customers, led by Mr. Maurice Shan, while average-income and professional segments contribute the majority of orders.

---

***  DAX Measures Included
This project uses **40+ DAX measures**, including:
- Time intelligence (YTD, QTD, Previous Month, Rolling Revenue)
- Target vs Actual calculations
- Return rate and profitability metrics
- Dynamic filtering using `ALL`, `FILTER`, and `CALCULATE`
- What-if parameter–based pricing analysis

*** Dataset Information
- Source: **Adventure Works sample dataset (Bike Garage)**
- Data includes:
  - Sales transactions
  - Products and categories
  - Customers and demographics
  - Returns data
  - Calendar / Date dimension

*(Dataset size reduced for GitHub upload purposes)*

---

*** How to Use This Project
1. Clone or download this repository  
2. Open the `.pbix` file using **Power BI Desktop**
3. Refresh the data if required
4. Use slicers, filters, and parameters to explore insights

---

*** Key Learning Outcomes
- Writing and managing advanced **DAX measures**
- Building **data models** and defining relationships
- Implementing **time intelligence** calculations
- Designing **business-focused dashboards**
- Documenting Power BI projects using **GitHub**

---

👤 Author
**Pavan Kumar**  
Aspiring Data Analyst | Power BI Developer  

---

** Feedback **
If you find this project useful, feel free to ⭐ the repository or share your feedback.

** Acknowledgement **
This project is created for learning and portfolio purposes, inspired by online tutorials and publicly available datasets.






