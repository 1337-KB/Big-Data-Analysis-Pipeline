# Big-Data-Analysis-Pipeline
This project involves simulating a real world dataset and it's inconsistencies and running through the medallion architecture(Bronze, Silver, Gold)
and analysing the results and presenting in a dashboard
The repository contains the stages through which the data is going to be processed:
**notebooks/01_bronze_data_generation.ipynb** — Generates mock data and writes to Bronze Delta tables. This is one team member's primary ownership.
**notebooks/02_silver_processing.ipynb** — Reads Bronze, cleans and transforms into Silver, then joins/aggregates into Gold tables.
**notebooks/03_gold_analysis_eda.ipynb** — EDA plots and summary stats on Gold tables. Feeds into the dashboard and report.
