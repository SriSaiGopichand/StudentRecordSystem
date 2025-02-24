# STUDENT RECORD SYSTEM

## Overview
This project focuses on building a data transformation pipeline to aggregate subject pass percentages across multiple datasets using **Informatica PowerCenter**. The pipeline extracts data from multiple sources, applies specific business rules for aggregation, and loads the transformed data into a centralized target repository. The primary goal is to compute the average pass percentage per subject, considering various filters and conditions to ensure accurate reporting and efficient processing.

## Key Features

### 1. Data Extraction and Transformation
- **Source Integration**: The pipeline extracts raw data from various input sources, including student performance records and subject-related information.
- **Transformation Logic**: The main transformation involves calculating the pass percentage for each subject by aggregating scores and dividing by total students. This is achieved using the **Aggregator Transformation** in Informatica to group the data by subject and compute the necessary metrics.

### 2. Aggregation and Data Cleansing
- **Custom Aggregation**: Using **Aggregator Transformations**, the data is grouped by subject, and pass percentage is calculated for each subject category.
- **Data Cleansing**: Invalid or incomplete records are filtered out during the transformation process to ensure only valid data reaches the target repository.

### 3. Efficient Data Processing
- **Parallel Processing**: The pipeline is designed to handle large datasets efficiently by using **Partitioning** in Informatica PowerCenter. This allows for parallel execution, speeding up the transformation process without compromising accuracy.
- **Indexing**: To further optimize data retrieval and performance, **indexing** techniques are applied to frequently accessed fields.

### 4. Loading and Target Data Integration
- **Bulk Data Load**: After aggregation, the transformed data is loaded into the target repository using **Informatica’s Bulk Load** capabilities. This ensures that the data is written efficiently and accurately into the final tables.
- **Table Truncation**: To ensure that outdated data is not carried over, the target tables are truncated before each bulk load, maintaining the integrity of the dataset.

### 5. Monitoring and Error Handling
- **Session Logs**: Detailed session logs are maintained throughout the pipeline execution. These logs track every step of the transformation, from data extraction to loading. Errors are logged with specific error codes and descriptions for debugging.
- **Error Handling**: Any data inconsistencies or transformation issues are logged for manual review, ensuring that errors are caught and handled promptly.

### 6. Performance Optimization
- **Resource Management**: Logs indicate that session and memory resource allocation were closely monitored to ensure smooth execution. Optimizations include careful management of the session cache size, disk space, and CPU allocation.
- **Caching Mechanisms**: **Lookup Caching** and **Persistent Cache** were used in appropriate steps to reduce the time spent querying large tables and enhance processing speed.

## Key Informatica Components Used:
- **Aggregator Transformation**: To calculate pass percentages and group data by subject.
- **Joiner Transformation**: To merge data from different sources before aggregation.
- **Expression Transformation**: For implementing custom business logic and handling calculations.
- **Sorter Transformation**: To sort data before loading into the target repository.
- **Session & Workflow**: To orchestrate the overall data flow and monitor the execution.
- **Error & Session Log Files**: For monitoring, auditing, and troubleshooting.

## Outcome:
- **Accurate Reporting**: The pipeline generates detailed reports showing pass percentages for each subject, allowing for further analysis on performance trends.
- **Scalable & Efficient**: The pipeline is built to handle large datasets efficiently, ensuring it can be scaled as needed for increased data volume or additional subjects.
- **Optimized Performance**: Through parallel processing, indexing, and cache optimization, the transformation process runs smoothly without excessive resource consumption.
