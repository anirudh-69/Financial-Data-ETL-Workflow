# Financial Data ETL Workflow

This project demonstrates an **ETL (Extract, Transform, Load)** workflow for processing financial data using the **Alpha Vantage API**, **Mage**, and **PostgreSQL**. The workflow is designed to fetch, transform, and store financial intraday stock data, enabling streamlined data analysis.

![ERD](images/IntradayERD.png)

---

## Project Overview

### Workflow Steps
| **Step**                | **Description**                                                                              |
|-------------------------|----------------------------------------------------------------------------------------------|
| **1. Data Retrieval**   | Fetches intraday time series for the past month (1-minute intervals) for selected stocks.    |
| **2. Raw Data Storage** | Stores raw data in a PostgreSQL database with an ingestion timestamp.                        |
| **3. Data Aggregation** | Computes daily averages for key columns (open, close, high, low, volume) by date and ticker. |
| **4. Deduplication**    | Removes duplicate rows while retaining aggregated columns.                                   |
| **5. Data Export**      | Exports transformed daily data back into the database for analysis.                          |

### Database Design
Two tables are used in the database:
1. **Raw Data Table**: Stores the raw intraday stock data.
2. **Transformed Data Table**: Stores the aggregated daily averages.

---