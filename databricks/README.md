# End-to-End Pipeline - Retail Data Lakehouse Project

This pipeline automates the full data flow from the raw ingestion layer (Bronze) to the final analytics-ready tables (Gold) in a retail data lakehouse setup. Everything runs through a Databricks Workflow, making the whole process smooth and hands-free once it's set up.

## Workflow Diagram

<div align="center">
    <img src="https://raw.githubusercontent.com/juancarlosierrac/RetailDataLakehouse-AzureDataEngineeringProject/main/images/End-to-End-Pipeline.png" 
         alt="End to End Pipeline Project" 
         width="800px"/>
</div>  

## Workflow Overview

The pipeline consists of three main layers: Bronze, Silver and Gold. This section focuses on the final Gold layer, where the data is prepared for analytics and reporting.

The logic for each table is implemented in its corresponding notebook. If you want to see the details, check the attached notebooks in this repository.

## Gold Layer

### Gold Products - Slowly Changing Dimension (Type 2)

<div align="center">
    <img src="https://raw.githubusercontent.com/juancarlosierrac/RetailDataLakehouse-AzureDataEngineeringProject/main/images/Gold_Products_DLT.png"  
         alt="Gold Products DLT"  
         width="800px"/>
</div>  

We track changes to products over time. If a product's name or other attribute changes, we keep the old version and add the new one. This helps understand how things evolved.

### Gold Orders - Fact Table

We joined the orders data with the product and customer dimension tables to create a fact table. This table is ready for analysis and reports, as it contains all the keys and necessary fields linked together.

### Gold Customers - Slowly Changing Dimension (Type 1)

For customers, we just care about the most recent info. When there’s a change, we replace the old data instead of keeping history. It’s simpler and faster for cases where tracking changes isn’t necessary.
