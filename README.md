# Ecommerce-Data-Engineering-Gcp

# Spark Project: Real-World E-Commerce Data Analysis

## Overview

In this project, we embark on a detailed exploration of a real-world e-commerce dataset using Apache Spark. The dataset is from Olist, a Brazilian e-commerce platform, and covers various aspects of online sales, including orders, customers, products, sellers, payments, reviews, and geolocation data.

The project is structured into five modules, demonstrating end-to-end data processing: from ingestion and cleaning to integration, optimization, and serving. This simulates a production-grade data engineering pipeline on a Spark cluster (e.g., Google Dataproc).

### Key Objectives
- Ingest and explore raw data.
- Clean and transform data for analysis.
- Integrate multiple datasets and perform aggregations.
- Optimize Spark performance for efficiency.
- Serve processed data for downstream applications.

### Dataset
- **Source**: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Files Included**:
  - `olist_customers_dataset.csv`
  - `olist_geolocation_dataset.csv`
  - `olist_order_items_dataset.csv`
  - `olist_order_payments_dataset.csv`
  - `olist_order_reviews_dataset.csv`
  - `olist_orders_dataset.csv`
  - `olist_products_dataset.csv`
  - `olist_sellers_dataset.csv`
  - `product_category_name_translation.csv`
- **Description**: Contains details on orders (timestamps, status), customers (location, unique ID), products (categories, dimensions), sellers, payments (methods, installments), reviews (scores, comments), and geolocation (ZIP codes, lat/long).

The dataset schema includes relationships like:
- Orders linked to customers, items, payments, and reviews.
- Items linked to products and sellers.
- Geolocation for customer and seller ZIP codes.

## Project Modules

The project is divided into Jupyter notebooks (`.ipynb`) for each module, running PySpark on a Dataproc cluster. Below is an overview based on the project documentation.

### Module 1: Data Ingestion and Exploration
- Set up a production-grade industry approach.
- Store data into HDFS/Object Storage.
- Use Spark DataFrames for scalable operations.
- Exploration focuses on practical business use cases.
- Load data into Spark, infer schema, count rows, perform basic EDA (e.g., show samples, calculate delivery times).

### Module 2: Data Cleaning and Transformation
- This module focuses on real-world data engineering practices for cleaning and transforming data at scale using PySpark.
- Steps:
  1. Identify issues: Missing values, duplicates, invalid data.
  2. Handle missing values: Drop or fill null values, impute.
  3. Standardize formats: Convert date/time, normalize categorical fields.
  4. Data type correction: Correct data types if there are issues for each column.
  5. Deduplication: Remove duplicate records.
  6. Data Transformation: Apply feature engineering.
  7. Store cleaned data: Store in HDFS, in Parquet.
- Address quality issues and transform the data in a structured format.
- Handling of nulls, standardize dock symbols.
- Numerical & scale values.
- Create new features.

### Module 3: Data Integration and Aggregation
- Combine data from multiple tables to create a unified dataset.
- Perform joins, aggregate data, compute metrics.
- Resolve any inconsistencies from data.
- Caching and optimizing queries for performance.
- Send a lot of time and understand data in-depth.
- Aggregations: e.g., Order volume by state, revenue per seller.
- Create new features like delivery status flags, customer segments, order day types (weekday/weekend).

### Module 4: Performance Optimization
- Enhance the efficiency of data processing tasks.
- Use broadcasting for small joins.
- Skew handling.
- Utilize caching for iterative operations.
- Optimizing the Spark configuration.
- Key considerations: Cluster resources (master/workers), disabled features (no autoscaling), optimization strategies (shuffle partitions, broadcast thresholds).
- Techniques: Broadcast joins, sort-merge joins, bucket joins, skew handling.

### Module 5: Data Serving
- Make the processed data available.
- Export transformed data to an external system/databases.
- Create visualizations to represent data trends & patterns.
- Save data as Parquet in HDFS/GCS, Hive tables, or CSV.
- Objective: Save and retrieve processed data efficiently for analysis.

## Technologies Used
- **Apache Spark (PySpark)**: For data processing, transformations, and aggregations.
- **HDFS/GCS**: For storage.
- **Google Dataproc**: Cluster management (n2-standard-4 machines, no autoscaling).
- **Jupyter Notebooks**: For development and documentation.
- **Libraries**: PySpark SQL functions (e.g., `datediff`, `when`, `broadcast`).

## Setup Instructions

1. **Prerequisites**:
   - Apache Spark installed (or use a managed service like Dataproc).
   - Access to HDFS or cloud storage (e.g., GCS).
   - Python 3.x with PySpark.

2. **Clone the Repository**:
