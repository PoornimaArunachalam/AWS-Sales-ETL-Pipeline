# AWS Sales ETL Pipeline

## Project Overview
This project implements a basic cloud-based ETL pipeline using Amazon Web Services (AWS) to process sales transaction data.

The pipeline extracts sales data from an Amazon S3 bucket, transforms the data using AWS Glue, and loads the processed data into a data warehouse for analysis using Amazon Athena.

## Technologies Used
- Amazon S3 – Data storage
- AWS Glue – ETL processing
- AWS IAM – Access management
- Amazon Athena – SQL querying and reporting
- Python – Data transformation
- SQL – Data warehouse queries
- GitHub – Version control

## Project Architecture

CSV Sales Data → Amazon S3 → AWS Glue → Processed Data (Parquet) → Amazon Athena → Aggregated Sales Report

## Data Warehouse Design

### 1. Product Dimension Table
- product_id
- product_name
- category

### 2. Sales Fact Table
- sale_id
- sale_date
- product_id
- quantity
- unit_price
- sales_amount

## ETL Workflow

1. Upload the sales CSV file to Amazon S3.
2. Extract sales data using AWS Glue.
3. Remove zero-dollar sales records.
4. Separate product information into the Product dimension.
5. Store transactional information in the Sales fact table.
6. Save processed data in Parquet format.
7. Query the warehouse using Amazon Athena.
8. Generate an aggregated sales report by product.

## Final Output

The final report displays:
- Product ID
- Product name
- Category
- Total quantity sold
- Total sales amount

## AWS Resources
- Amazon S3 bucket
- AWS Glue ETL job
- IAM service role
- Amazon Athena database and tables

## Author
Poornima A
