# Global Fashion Retail Sales - Data Warehouse Pipeline

## 🧩 Project Overview

This project implements an end-to-end data pipeline for a **Global Fashion Retailer**, focusing on cleansing and modeling retail sales data to deliver business-ready insights. The pipeline loads data from multiple CSV sources into a **Snowflake Data Warehouse**, applying a multi-layered approach (Bronze, Silver, Gold) and generating insights via **Power BI**.

---

## 🎯 Business Goal

- **Objective**: Provide actionable insights to help the business identify sales trends, customer behaviors, and the impact of discounts.
- **Key Insight**: Business-ready views allow teams to spot high-performing stores, top-selling products, and discount-driven sales patterns.

---

## 📊 Data Sources

- **CSV Files**:
  - `Products.csv` - Product details
  - `Customers.csv` - Customer information 
  - `Transactions.csv` - Sales transactions 
  - `Discounts.csv` - Discount codes and values
  - `Stores.csv` - Store locations and metadata

### Data Challenges:
- Missing or invalid sale prices and customer data
- Non-standard date formats
- Duplicate or inconsistent records
- Unnormalized text fields

---

## 🏗️ Data Pipeline Architecture

### 🔶 Bronze Layer (Raw Data)
- Load raw CSV data as-is into Snowflake tables.
- No transformations applied.

### ⚪ Silver Layer (Cleansed Standardized Data)
- Data cleansing:
  - Remove duplicates, NULLs, and invalid entries.
  - Normalize product, customer, and store data.
  - Standardize discount codes and sale dates.
- Data enrichment:
  - Derived columns (e.g., total discount, net sales).
- Batch load into Snowflake standardized tables.

### 🟡 Gold Layer (Business-Ready Views)
- Apply business logic:
  - Integrate datasets across dimensions.
  - Calculate KPIs (e.g., net revenue, discount impact).
  - Create aggregated views (star schema).
- Ready for reporting & analytics.

---

## 🛠️ Tools & Technologies

- **Snowflake**: Cloud Data Warehouse
- **Apache Airflow**: Orchestration of batch pipelines
- **Docker**: Containerized Airflow setup
- **Power BI**: Business Intelligence and Reporting
- **Python**: ETL scripts and data wrangling
- **dbt** : Data Build tool

---

## 📅 ELT Process

1. **Ingest**  
   - CSV ➡ Snowflake Bronze tables via Airflow.

2. **Cleanse & Transform**  
   - Bronze ➡ Silver (clean, standardize, enrich).

3. **Modeling**  
   - Silver ➡ Gold (build fact/dim tables and views).

4. **Consume**  
   - Gold Layer ➡ Power BI dashboards.

---
