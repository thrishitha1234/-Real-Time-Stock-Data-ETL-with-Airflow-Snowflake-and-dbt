# 🚀 Real-Time Stock Price Analytics Pipeline using Airflow, Snowflake, dbt & Superset

## ✨ Why I Built This Project

With the stock market being fast-moving and volatile, I wanted to build a **real-time analytics pipeline** that could track and visualize patterns in stock prices. As someone passionate about both finance and data engineering, I chose this project to simulate how enterprise teams build **scalable ELT systems** that power BI dashboards and drive decision-making.

This pipeline takes **raw stock data** (NVDA, MSFT), ingests it automatically using **Apache Airflow**, models it with **dbt**, stores it in **Snowflake**, and visualizes it using **Superset dashboards**.

Through this project, I gained hands-on experience orchestrating automated workflows and managing data lifecycle from **API ingestion to insight delivery** — a vital skill set for roles in **Data Engineering** and **Analytics**.

---

## 🔧 Tech Stack

| Tool/Technology | Role |
|------------------|------|
| Python           | API requests, data handling |
| Apache Airflow   | Workflow orchestration (ETL scheduling) |
| Snowflake        | Cloud data warehouse |
| dbt              | Data modeling and transformation |
| Apache Superset  | Interactive BI dashboarding |
| Docker           | Containerized development and deployment |

---

## 🔄 Project Architecture

📌 This diagram shows the full flow from ingestion to visualization:


<img width="935" height="358" alt="image" src="https://github.com/user-attachments/assets/8fa363fe-422c-4571-a695-2b3a4a18c947" />


---

## 🔁 Workflow Overview

1. **Data Ingestion**
   - Real-time stock prices fetched every 10 minutes using Alpha Vantage API
   - Managed by **Airflow DAG 1**

2. **Data Loading**
   - Ingested into `STOCK_PRICE` table in **Snowflake**
   - Uses `MERGE` SQL for efficient upserts

3. **Data Transformation**
   - **Airflow DAG 2** runs dbt models:
     - Calculates 7-day and 30-day moving averages
     - Computes RSI (Relative Strength Index)
   - Output tables: `STOCK_ANALYTICS`, `MOVING_AVG`, `RSI_TABLE`

4. **Data Visualization**
   - Apache Superset connects to Snowflake
   - Dashboards visualize trends, RSI, and closing prices

---

## 📊 Example Dashboards

Coming soon — dashboards with:
- Historical close price trends
- RSI for NVDA and MSFT
- 7-day vs. 30-day moving average patterns

---

## 📁 Folder Structure

