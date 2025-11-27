# 📱 Mobile Sales Dashboard (Power BI)
Power BI • DAX • Power Query • Data Modelling • Sales Analytics

A complete end-to-end Power BI dashboard analyzing mobile phone sales across India.
This project transforms raw transaction data into an interactive analytical report to uncover brand performance, customer behavior, payment patterns, and city-based sales distribution.

---

## 📌 Dashboard Preview

![Dashboard](Mobile%20Sale%20Dashboard.png)

---

## 📑 Table of Contents
- [Project Overview](#project-overview)
- [Business Problem](#business-problem)
- [Objectives](#objectives)
- [Dataset Overview](#dataset-overview)
- [Initial Observations](#initial-observations)
- [Data Cleaning and Transformation](#data-cleaning-and-transformation)
- [Data Model & DAX Measures](#data-model-&-dax-measures)
- [Key Insights](#key-insights)
- [Dashboard Features](#dashboard-features)
- [Project Files](#project-files)
- [How to Use](#how-to-use)
- [Limitations](#limitations)
- [Future Enhancements](#future-enhancements)

---

## 📘 Project Overview
This Power BI dashboard helps retail and sales teams understand:

- How sales vary by brand, model, and city  
- Which payment methods customers prefer  
- Which days drive the most business  
- How customer ratings correlate with sales  
- How monthly sales fluctuate across the years  

The dashboard is fully interactive with dynamic slicers for year, brand, payment method, and model.

---

## ❗ Business Problem
Mobile retailers need answers to critical questions:

- Which brands are performing the best?  
- Which cities contribute most to total revenue?  
- When are customer purchases highest?  
- Are certain payment methods becoming more popular?  
- How do customers perceive the products (ratings)?  

This dashboard consolidates these insights into one unified view.

---

## 🎯 Objectives
- Clean and prepare raw sales data using Power Query  
- Build a Power BI data model  
- Create DAX measures for KPIs and analysis  
- Develop interactive visuals for better decision-making  
- Identify customer and product trends  

---

## 📁 Dataset Overview
**Records:** 3,835  
**Columns:** 14  
**Format:** Excel  
**Period:** 2021–2024  

### Key Columns
- Brand  
- Model  
- Quantity  
- Price  
- Payment Method  
- Customer Rating  
- City  
- Date components (Year, Month, Day)  

---

##  Initial Observations
- Date was split across three columns (Year, Month, Day) – needed merging  
- Day names included inconsistencies (e.g., “Fr”, “Fri”, “Friday”)  
- No direct revenue/profit column was present  
- Dataset contained no blanks or nulls  
- Data was well-structured but needed standardized columns for analysis  

---

## 🧹 Data Cleaning and Transformation
Performed in Power Query.

### Steps
1. Column Quality Check  
2. Merged Year, Month, and Day into a single Date column  
3. Standardized Day Name values  
4. Created a Calendar Table  
5. Verified duplicates (none found)  
6. Created calculated column for Total Sales:  
   `Total Sales = Quantity * Price`  
7. Final load into the Power BI data model  

---

## 📐 Data Model & DAX Measures

### Key DAX Measures

```DAX
Total Sales := SUM(Sales[Total Sales])

Total Quantity := SUM(Sales[Quantity])

Total Transactions := COUNTROWS(Sales)

Average Price := DIVIDE(SUM(Sales[Total Sales]), SUM(Sales[Quantity]))

Average Rating := AVERAGE(Sales[Customer Rating])
```

---

## 📊 Key Insights

### Sales Trends
- Sales remained stable across the 3-year period  
- February and September showed slight dips  
- Thursday and Saturday were the best-performing days  

### Brand Insights
- Vivo and Apple dominated in revenue  
- Best-selling models:
  - Vivo S1 – ₹6.6M  
  - Vivo V20 – ₹6.4M  
  - iPhone 11 – ₹5.7M  

### Customer Behavior
- Most ratings were 4–5 stars  
- Indicates high customer satisfaction  

### Payment Insights
- Cash and UPI together accounted for over 50% of transactions  

### Geographic Insights
- Sales were strongest in major metro cities  
- Indicates higher demand in urban regions  

---

## 🖥 Dashboard Features

### KPI Cards
- Total Sales  
- Total Quantity  
- Total Transactions  
- Average Price  

### Filters / Slicers
- Year  
- Month  
- Brand  
- Model  
- Payment Method  

### Visuals
- Map visual for city-wise sales  
- Line chart for monthly quantity trends  
- Bar charts:
  - Customer Ratings  
  - Sales by Day  
  - Sales by Brand  
  - Sales by Mobile Model  
- Pie chart for Payment Mode distribution  
- Detailed table for model-level breakdown  

---

## 📂 Project Files

```
Mobile_Sales_Dashboard/
│
├── Mobile Sales Dashboard PB.I.pbix
├── Mobile Sales Raw Data.xlsx
├── Mobile Sale Dashboard.png
├── Total Sales.png
├── Transactions.png
├── Average.png
├── Max Icon.png
├── Filter.png
├── Mobile Logo.png
└── README.md
```

---

## 🧭 How to Use
1. Download the `.pbix` file  
2. Open in Power BI Desktop (latest version recommended)  
3. Ensure data model loads correctly  
4. Use slicers to explore different segments  
5. Publish to Power BI Service if needed  

---

## ⚠ Limitations
- No profit or cost column available  
- Rating scale limited to 1–5 without additional review context  
- Dataset lacks return/cancellation information  

---

## 🚀 Future Enhancements
- Add forecasting with DAX or Power BI AI visuals  
- Add customer segmentation using clustering  
- Introduce profitability analysis with additional cost data  
- Expand geographic granularity with GPS coordinates  
