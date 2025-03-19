# 📊 Stock & Financial Data ELT Pipeline with DBT

## Overview
This project implements an **end-to-end ELT pipeline** to extract, load, and transform daily stock price data for the **top 10 global companies** (e.g., AAPL, MSFT, AMZN, GOOGL, etc.) using modern data engineering tools. The pipeline automates data ingestion, cleansing, modeling, and reporting to deliver business-ready insights for **finance teams, traders, and analysts**.

---

## 🎯 Business Goal
The objective is to enable financial insights through:
- **Trend Analysis**: Identify long-term price patterns.
- **Price Volatility**: Highlight periods of high/low volatility.
- **Investment Opportunities**: Compare stock performance across companies over time.

---

## 🛠 Tech Stack

| Component          | Technology                      |
|--------------------|---------------------------------|
| **Ingestion**      | Python (`yfinance`, `pandas`)   |
| **Data Warehouse** | Snowflake)                      |
| **Transformation** | DBT (staging + marts + tests)   |
| **Orchestration**  | Apache Airflow (Dockerized)     |
| **Visualization**  | Power BI                        |

---

## ⚙️ Pipeline Architecture

1. **Source**:  
   - Extract daily stock data from **Yahoo Finance** using `yfinance`.

2. **Bronze Layer**:  
   - Raw data is ingested and stored as-is in PostgreSQL.

3. **Silver Layer**:  
   - Cleanse and standardize the data (handle missing values, normalize date formats, enrich data).

4. **Gold Layer**:  
   - Business-ready models using DBT (e.g., `fact_stock_prices` table).

5. **Consumption**:  
   - Power BI dashboards visualize stock performance and trading volume.

---

## 🗂 Project Structure

```plaintext
.
├── dags/                         # Airflow DAGs
│   └── stock_pipeline_dag.py
├── dbt/                          # DBT project
│   ├── models/
│   │   ├── staging/
│   │   │   └── stg_stock_prices.sql
│   │   └── marts/
│   │       └── fact_stock_prices.sql
│   ├── tests/
│   │   └── schema_tests.yml
├── scripts/
│   └── ingest_stock_data.py      # Python ingestion script (yfinance)
├── docker-compose.yml            # Docker Compose for Airflow & PostgreSQL
├── requirements.txt              # Python dependencies
├── README.md                     # Project documentation
└── powerbi_dashboard/            # Power BI .pbix file

```


