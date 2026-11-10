# E-commerce Data Engineering & Power BI Analytics

Project Overview

Built an end-to-end analytics solution using Azure Data Lake Storage
Gen2, Microsoft Fabric Lakehouse, Fabric Data Pipeline, Spark
SQL/PySpark, Delta Lake and Power BI.

End-to-End Workflow

1.	Source data -- ADLS Gen2
○	Stored four CSV files in Azure Data Lake Storage Gen2:
customers.csv, orders.csv, order_items.csv and
products.csv.

2.	Ingestion -- Microsoft Fabric Pipeline
○	Created a Fabric connection to the ADLS Gen2 storage account.
○	Configured Copy activities to load the four CSV files into the
ecom_lakehouse Lakehouse.
○	Ran the pipeline successfully and landed the source data in the
Bronze layer.

3.	Lakehouse -- Delta Lake
○	Created the ecom_lakehouse in Microsoft Fabric.
○	Used Delta tables to store and process data across the Bronze,
Silver and Gold layers.

4.	Bronze layer -- Raw ingestion
○	Loaded the source data with minimal transformation.
○	Created raw tables: bronze_customers_raw, bronze_orders_raw,
bronze_order_items_raw and bronze_products_raw.

5.	Silver layer -- Cleansing and transformation
○	Used a Fabric notebook with Spark SQL to clean and standardize
the Bronze data.
○	Applied data type conversions, date formatting, whitespace
removal, text standardization and null/invalid-record filtering.
○	Created the cleaned Delta tables: silver_customers,
silver_orders, silver_order_items and silver_products.

6.	Gold layer -- Business-ready data
○	Joined the Silver tables to create an enriched orders view.
○	Calculated delivery delay and aggregated business KPIs.
○	Created the Gold Delta table: gold_order_kpis.

7.	Semantic model and Power BI
○	Created a semantic model using the Gold layer.
○	Connected Power BI to the semantic model.
○	Built KPI cards, charts and analytical views for business
reporting.
○	Published the Power BI report.

Architecture

ADLS Gen2 (CSV files) → Fabric Data Pipeline (Copy activity) → Lakehouse Bronze → Notebook / Spark SQL → Silver → Enriched view → Gold KPI table → Semantic model → Power BI report
Key Technologies

●	Azure Data Lake Storage Gen2
●	Microsoft Fabric Data Pipeline
●	Microsoft Fabric Lakehouse
●	Fabric Notebooks (PySpark / Spark SQL)
●	Delta Lake and Medallion Architecture
●	Power BI Semantic Model and Reports
