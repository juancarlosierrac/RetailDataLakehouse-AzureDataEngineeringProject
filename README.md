# **Retail Data Lakehouse - Azure Data Engineering Project**

## **Introduction**
This project implements a complete end-to-end data engineering solution using Azure Databricks and the Medallion Architecture. The use case simulates a Retail company working with multiple transactional and reference data sources, ingested and processed incrementally in a unified Lakehouse platform. The goal is to build a scalable and governed data pipeline from raw data to business insights.

---

## **Project Overview**
The project processes a retail dataset consisting of customer orders, product catalogs, and regional information. Data is received in multiple versions (e.g., `orders_first.parquet`, `orders_second.parquet`) to simulate incremental data loads over time.

### Key Features:
- **Ingestion** from GitHub and Azure Storage in Parquet format.
- **Bronze Layer**: Raw incremental ingestion using Spark Structured Streaming and automated ingestion pipelines.
- **Silver Layer**: Cleansed and enriched data, join operations across datasets, and business rules applied.
- **Gold Layer**: Star Schema modeling with Dimension and Fact tables including **Slowly Changing Dimensions** (SCD Types 1 & 2) using **Delta Live Tables**.

The pipeline concludes by loading the curated data into Azure Synapse Analytics, which feeds interactive dashboards built in Power BI.

---

## **Architecture**
<div align="center">
    <img src="https://raw.githubusercontent.com/juancarlosierrac/SQLDB-AzureDataEngineeringProject/main/images/Retail Data Lakehouse - Azure Data Engineering Project.png" 
         alt="Retail Data Lakehouse Architecture" 
         width="800px"/>
</div>  

---

## **Objective**
To demonstrate a real-world data lakehouse solution for a retail business, focusing on:

- **Incremental Data Processing**
- **Data Governance with Unity Catalog**
- **Building Reliable ETL Pipelines**
- **Dimensional Modeling for BI**
- **Real-time Processing Capabilities**

This hands-on implementation provides a foundation for building scalable analytics platforms using Azure and Databricks.

---

## **Technologies Used**  
- Azure Databricks  
- Delta Lake & Delta Live Tables (DLT)  
- Azure Data Lake Gen2  
- Azure Synapse Analytics  
- Unity Catalog  
- Power BI  
- Azure Key Vault  
- GitHub (as data source)  
- Apache Spark (Structured Streaming)  

---

This project is designed to replicate real-world retail data engineering practices, with inspiration from best practices shared by Ansh Lamba.
