# End-to-End Azure Data Engineering Project

## Overview

This project demonstrates the design and implementation of a modern **Data Engineering pipeline** using Microsoft Azure and Azure Databricks. The solution follows the **Medallion Architecture (Bronze, Silver, Gold)** pattern to ingest, transform, and model sales data for analytics and reporting.

The pipeline automates data ingestion from source systems, performs incremental data processing, applies business transformations, and builds a dimensional model optimized for analytical workloads.

---

### Data Flow

```text
GitHub CSV Data
       │
       ▼
Azure SQL Database
       │
       ▼
Azure Data Factory
       │
       ▼
Bronze Layer (ADLS Gen2 - Parquet)
       │
       ▼
Azure Databricks (PySpark)
       │
       ▼
Silver Layer (Cleaned & Transformed Data)
       │
       ▼
Gold Layer (Delta Lake + Star Schema)
       │
       ▼
Analytics & Reporting
```

---

## Technologies Used

### Cloud Services

* Microsoft Azure
* Azure Data Factory
* Azure SQL Database
* Azure Data Lake Storage Gen2
* Azure Databricks

### Data Engineering

* Apache Spark
* PySpark
* Delta Lake
* Unity Catalog
* Medallion Architecture
* Slowly Changing Dimensions (SCD Type 1)

### Languages

* Python
* SQL

### Data Formats

* CSV
* Parquet
* Delta

---

## Key Features

### Data Ingestion

* Loaded source sales data from GitHub into Azure SQL Database. 
* Built parameterized Azure Data Factory pipelines for reusable ingestion.
* Implemented production-style ETL workflows.

### Incremental Data Processing

* Designed an incremental loading framework using:

  * Watermark tables
  * Stored procedures
  * Lookup activities
  * Dynamic SQL queries

* Processed only newly arrived records instead of reloading the full dataset.

### Data Lake Implementation

Implemented a three-layer Medallion Architecture:

#### Bronze Layer

* Raw data storage
* Historical data retention
* Incremental ingestion

#### Silver Layer

* Data cleansing
* Data standardization
* Business transformations
* KPI generation

#### Gold Layer

* Analytics-ready datasets
* Star schema implementation
* Delta tables

### Databricks Transformations

Used PySpark to:

* Read Parquet datasets from ADLS Gen2
* Create derived business columns
* Generate KPIs
* Perform aggregations
* Apply dimensional modeling

Example transformations:

* Created `Model_Category` from `Model_ID`
* Calculated `Revenue Per Unit`
* Generated analytical summaries

### Data Governance

Implemented Unity Catalog for:

* Data governance
* Access control
* Metadata management
* Data lineage

### Dimensional Modeling

Built a Star Schema consisting of:

#### Dimension Tables

* Dim_Model
* Dim_Branch
* Dim_Dealer
* Dim_Date

#### Fact Table

* Fact_Sales

Features implemented:

* Surrogate keys
* Incremental dimension loading
* SCD Type 1 processing

### Delta Lake Implementation

Implemented Delta Lake for:

* ACID transactions
* Reliable upserts
* Merge operations
* Incremental processing

---

## Engineering Concepts Demonstrated

* ETL / ELT Pipelines
* Incremental Loading
* Change Data Capture (CDC)
* Medallion Architecture
* Data Lakehouse Design
* Star Schema Modeling
* Data Governance
* Delta Lake
* Slowly Changing Dimensions (SCD Type 1)
* Surrogate Key Generation
* Data Quality and Validation
* Cloud Data Engineering

---

## Business Value

This solution simulates a real-world enterprise data platform by:

* Automating data ingestion and processing
* Reducing unnecessary full data reloads
* Improving data quality and governance
* Providing analytics-ready datasets
* Demonstrating scalable cloud data engineering practices

---

## Skills Demonstrated

### Azure

* Azure Data Factory
* Azure SQL Database
* Azure Data Lake Storage Gen2
* Azure IAM & Access Control

### Databricks

* PySpark
* Delta Lake
* Unity Catalog
* Notebook Development

### Data Engineering

* Data Modeling
* ETL Development
* Incremental Processing
* Pipeline Orchestration
* Performance Optimization

### Programming

* Python
* SQL
* Spark SQL

---

## Future Enhancements

* Automated data quality checks
* Delta Live Tables (DLT)
* Real-time streaming ingestion
* Power BI dashboard integration
* Monitoring and alerting framework

---

