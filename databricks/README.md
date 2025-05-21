# Bronze Incremental Pipeline - Databricks Workflow

This pipeline implements an incremental ingestion process using Databricks Workflows and Autoloader to populate the Bronze layer of a retail data lakehouse architecture. It is designed to efficiently handle new data arrivals from different parquet files and store them in a structured and scalable manner.

## Workflow Diagram

<div align="center">
    <img src="https://raw.githubusercontent.com/juancarlosierrac/RetailDataLakehouse-AzureDataEngineeringProject/main/images/Bronze_Incremental.png" 
         alt="Bronze Incremental Workflow Diagram" 
         width="800px"/>
</div>  

## Workflow Overview

The solution is implemented through a Databricks Workflow named `Bronze_Incremental`, which consists of two main notebooks:

### 1. Parameters

This notebook defines a dictionary with the available data sources: `orders`, `products`, and `customers`. The dictionary is passed as input to the next notebook, enabling a parameterized and reusable ingestion logic.

### 2. Bronze_Autoloader_iteration

This notebook receives the dictionary and iterates over each file type. It performs the following steps:

- Reads data incrementally using `Autoloader` with the `cloudFiles` source format.
- Uses a dynamic schema location and checkpoint for each file type.
- Writes the output to the Bronze layer using `Structured Streaming` with `trigger(once=True)`.

Each ingestion cycle is isolated by checkpoint to ensure exactly-once processing semantics.
