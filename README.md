# Retail Bank Customer Analytics
### SYST52461 – Big Data Storage and Analysis | Term Project


## Scenario
This project models a retail banking environment to analyze customer financial 
behaviour across accounts, transactions, and lending activity. Using mocked data 
designed to reflect realistic quality issues, we build an end-to-end pipeline 
through the medallion architecture (Bronze → Silver → Gold) in Databricks using 
PySpark.

## Tables
| Table | Description |
|---|---|
| `customers` | Customer demographics: age, province, income bracket, join date |
| `accounts` | Chequing/savings accounts linked to each customer |
| `transactions` | Deposits, withdrawals, and transfers tied to accounts |
| `loan_applications` | Mortgage, auto, and personal loan requests with approval outcomes |

**Key relationships:**
- `customers` → `accounts` via `customer_id`
- `accounts` → `transactions` via `account_id`
- `customers` → `loan_applications` via `customer_id`

## Notebooks
| Notebook | Description |
|---|---|
| `notebooks/01_bronze_data_generation.ipynb` | Generates mock data and writes to Bronze Delta tables |
| `notebooks/02_silver_processing.ipynb` | Cleans and transforms Bronze into Silver, then aggregates into Gold |
| `notebooks/03_gold_analysis_eda.ipynb` | EDA plots and summary statistics on Gold tables |

## Architecture
This project follows the **medallion architecture**:
- **Bronze** – Raw mocked data with intentional quality issues (nulls, type 
  mismatches, inconsistent formatting)
- **Silver** – Cleaned and standardized tables ready for joining
- **Gold** – Aggregated, analysis-ready tables that feed the dashboard and report

## Databricks
All tables are stored in a dedicated Databricks catalog and schema. The dashboard 
is built using the native Databricks Dashboards feature.
