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

##  Dashboards

<img width="1158" height="460" alt="image" src="https://github.com/user-attachments/assets/78b58ca0-8540-499e-bb0b-f31632df943d" />

Purpose:
The purpose of this dashboard is to enable users to analyze key stock performance
indicators, specifically for NVIDIA (NVDA) and Microsoft (MSFT) stocks. By tracking various
metrics such as the Relative Strength Index (RSI), moving averages, and closing prices, the
dashboard supports informed trading and investment decisions. It aims to help users assess
momentum, identify trends, and gauge price stability over time.
Usage:
• Investors and Traders who want to monitor stocks’ momentum and trend patterns to
make buy, hold, or sell decisions.
• Technical Analysts focusing on RSI to spot potential reversal points.
• Financial Analysts looking to identify and interpret trends for investment insights.
Dataset:
• Stock Prices: Historical daily stock prices for NVIDIA (NVDA) and Microsoft (MSFT),
including opening, high, low, and closing prices.
• RSI Data: Calculated daily RSI values for each stock, derived from the stock price dataset.
• Moving Averages: Calculated 30-day moving averages based on historical daily closing
prices to reflect short-term trends.

<img width="1031" height="424" alt="image" src="https://github.com/user-attachments/assets/fa91beef-cc42-467c-a98e-f8c196ad160f" />

Purpose:
This dashboard is designed to provide a filtered view of stock performance,
focusing on recent trends and specific stock symbols (e.g., NVDA and MSFT). It seems to
be aimed at tracking short-term stock movements.
Usage:
• Stock Close Prices: The first chart shows the closing price of NVDA over time, allowing
users to track its performance from September to November.
• Previous Month Comparison: The second chart compares the previous month's closing
prices for both NVDA and MSFT on specific dates, giving a side-by-side comparison of
these two stocks.
• 7-Day Stock Price History: The third chart shows the 7-day historical prices for both
NVDA and MSFT, helping users quickly assess short-term price fluctuations.
Dataset:
• Stock Prices: Historical daily stock prices for NVIDIA (NVDA) and Microsoft (MSFT),
including opening, high, low, and closing prices.
• RSI Data: Calculated daily RSI values for each stock, derived from the stock price dataset.
• Moving Averages: Calculated 30-day moving averages based on historical daily closing
prices to reflect short-term trends.

---

## 📁 Folder Structure

