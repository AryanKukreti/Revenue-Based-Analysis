# Vendor Performance Analysis
<div align="center"> <img src="https://raw.githubusercontent.com/AryanKukreti/Revenue-Based-Analysis/main/project-2.png" alt="Enterprise Vendor Performance Analytics System" width="600"> 



## Overview

This project analyzes vendor, brand, and inventory performance for a retail/wholesale business to identify profitability drivers, operational inefficiencies, and actionable opportunities for optimization. The analysis combines data ingestion pipelines, exploratory data analysis (EDA), statistical validation, and business-focused reporting to support data-driven decision-making.

The repository includes Python scripts for database ingestion and transformation, Jupyter notebooks for analysis, a Power BI dashboard for visualization, and a detailed analytical report.

## Business Objectives

The analysis was designed to address the following core business questions:

* Identify underperforming brands that may benefit from pricing or promotional adjustments.
* Determine top vendors contributing to sales and gross profit.
* Evaluate the impact of bulk purchasing on unit costs.
* Assess inventory turnover to reduce holding costs and inefficiencies.
* Compare profitability patterns between high-performing and low-performing vendors.

## Data Pipeline & Architecture

1. **Raw Data Ingestion**

   * CSV files are loaded into a SQLite database using an automated ingestion script.
   * Each CSV is stored as a separate table for modular querying and traceability.

2. **Vendor Summary Construction**

   * Purchase, sales, pricing, and freight data are merged into a unified vendor-level summary.
   * Derived metrics such as Gross Profit, Profit Margin, Stock Turnover, and Sales-to-Purchase Ratio are calculated for analysis.

3. **Data Cleaning & Filtering**

   * Missing values are handled and inconsistent records removed.
   * Loss-making and zero-sales records are excluded for profitability-focused insights.

## Exploratory Data Analysis (EDA)

Key EDA findings include:

* Presence of negative and zero gross profit values, indicating loss-making transactions and unsold inventory.
* Significant outliers in purchase price, sales price, and freight cost, reflecting premium products and logistics inefficiencies.
* Stock turnover ranges from very slow-moving items to rapidly selling products, highlighting uneven inventory performance.

Correlation analysis shows:

* Weak correlation between purchase price and sales or profit, suggesting pricing alone does not drive performance.
* Strong correlation between purchase and sales quantities, indicating efficient sell-through for stocked items.
* Weak relationship between stock turnover and profitability, implying that higher sales velocity does not always translate into higher margins.

## Key Insights & Findings

* **Brands with Optimization Potential**: 198 brands show low sales but high profit margins, making them strong candidates for targeted promotions or price optimization.
* **Vendor Concentration Risk**: The top 10 vendors account for ~65.7% of total purchase value, indicating over-reliance and potential supply chain risk.
* **Bulk Purchasing Advantage**: Large-volume purchases achieve ~72% lower unit costs compared to small orders, validating bulk pricing strategies.
* **Inventory Inefficiency**: Approximately $2.71M in capital is tied up in unsold or slow-moving inventory.
* **Profitability Models**: Low-performing vendors tend to have higher margins but lower volumes, while top vendors rely on scale and cost efficiency.

Statistical hypothesis testing confirms that profit margins between high-performing and low-performing vendors are significantly different, indicating distinct operational and pricing strategies.

## Tools & Technologies

* **Python**: Data ingestion, transformation, and analysis (pandas, sqlite3, SQLAlchemy).
* **SQL**: Vendor-level aggregations and joins.
* **Jupyter Notebook**: Exploratory data analysis and visualization.
* **Power BI**: Interactive dashboard for vendor and sales performance.
* **SQLite**: Lightweight analytical database.

## Repository Structure

```
├── data/                     # Raw CSV files
├── ingestion_db.py           # CSV-to-database ingestion script
├── get_vendor_summary.py     # Vendor-level aggregation and feature engineering
├── Exploratory Data Analysis.ipynb
├── Vendor Performance Analysis.ipynb
├── vendor_performance.pbix   # Power BI dashboard
├── Vendor Performance Report.pdf
└── inventory.db              # SQLite database (generated)
```

## Final Recommendations

* Re-evaluate pricing for low-sales, high-margin brands to increase volume without eroding profitability.
* Diversify vendor partnerships to reduce dependency on a small number of suppliers.
* Leverage bulk purchasing to maintain competitive pricing while improving margins.
* Actively manage slow-moving inventory through adjusted order quantities or clearance strategies.
* Strengthen marketing and distribution for low-performing vendors with strong margin potential.

## Outcome

By integrating automated data pipelines, robust analysis, and clear business insights, this project demonstrates how vendor and inventory data can be transformed into actionable strategies that improve profitability, reduce risk, and enhance operational efficiency.
