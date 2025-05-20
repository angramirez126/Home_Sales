
# Home Sales Project — SparkSQL & Big Data Optimization

This project involves analyzing home sales data using **PySpark** and **SparkSQL**. It was developed as part of a data engineering and analytics module, with a focus on querying large datasets, optimizing performance through caching and partitioning, and evaluating query efficiency in a big data environment.

## Project Summary

Using PySpark, I worked with a real estate dataset to compute aggregated metrics and enhance query performance. Key components of the project included:

- Creating temporary SQL views for analysis
- Writing SparkSQL queries to extract housing insights
- Caching data to reduce query time
- Partitioning the dataset for improved performance
- Benchmarking queries before and after caching
- Saving data in Parquet format and reloading for analysis

## Repository Contents

- `Home_Sales.ipynb` — Jupyter notebook with all code and analysis
- `home_sales_revised.csv` — Input dataset sourced from AWS S3
- `home_sales_partitioned/` — Output Parquet files partitioned by `date_built` (if available)

## Key Tasks

### 1. Data Loading and Setup

- Loaded the dataset from S3 into a Spark DataFrame
- Registered a temporary view named `home_sales` for use with SparkSQL

### 2. Data Analysis with SparkSQL

Answered the following business questions:

- Average price of four-bedroom homes sold per year
- Average price of 3 bed / 3 bath homes by year built
- Average price of 3 bed / 3 bath, two-floor homes ≥ 2,000 sqft by year
- Average price per view rating for homes with an average price ≥ $350,000

### 3. Caching and Performance Testing

- Cached the `home_sales` view
- Verified the cache with `spark.catalog.isCached()`
- Re-executed queries to measure performance improvement from caching

### 4. Partitioning and Parquet

- Partitioned the dataset by `date_built` and saved as Parquet
- Reloaded and queried the partitioned data using a new temp view

### 5. Cleanup

- Uncached the `home_sales` view
- Confirmed removal of cache

## Performance Insights

Caching significantly improved query performance on repeated executions. Partitioning by year (`date_built`) further enhanced performance for time-based queries, demonstrating best practices in Spark data optimization.

## Technologies Used

- Python
- PySpark
- SparkSQL
- Jupyter Notebook
- Parquet file format
- AWS S3 (data source)

## Final Notes

This project strengthened my skills in distributed data processing with Spark. It highlights how SQL-based analysis can be combined with optimization techniques like caching and partitioning to build scalable, high-performance data pipelines.
