# 🚀 AWS ETL Pipeline for Incremental JSON Data (S3 + Lambda + Glue + Athena)

A serverless data engineering project built on AWS to perform incremental ETL on nested JSON order data. This project demonstrates how to use AWS Lambda, S3, Glue, and Athena to flatten, transform, store, and query structured data efficiently.

## 📌 Project Overview

This ETL pipeline processes incoming JSON files containing customer orders:
- 🟡 Incoming JSON is uploaded to **Amazon S3**.
- 🧠 A **Lambda function** is triggered automatically, flattens the nested structure using Pandas, and converts the data to **Parquet** format.
- 🔄 The **Parquet file** is written back to another folder in S3.
- 🧭 A **Glue Crawler** updates the schema and populates a table in the AWS Glue Data Catalog.
- 🔍 You can then query the transformed data using **Athena**.

## 📁 Project Architecture

```text
+-------------------------+
|   JSON File in S3      |
|   (incoming_json_de/)  |
+-----------+------------+
            |
            v
+-------------------------+
|   AWS Lambda Trigger    |
|   - Flatten JSON        |
|   - Convert to Parquet  |
+-----------+------------+
            |
            v
+-------------------------+
|   Store to S3 (parquet) |
|   (parq_store_de/)      |
+-----------+------------+
            |
            v
+-------------------------+
|   AWS Glue Crawler      |
|   - Update Data Catalog |
+-----------+------------+
            |
            v
+-------------------------+
|   Athena (SQL Queries)  |
|   - Query via SQL       |
+-------------------------+
```

## 🧰 Tech Stack

- **Amazon S3**
- **AWS Lambda**
- **AWS Glue**
- **Amazon Athena**
- **Python (Pandas, PyArrow, Boto3)**

## 📂 Repository Structure

```bash
aws-etl-incremental-pipeline/
├── README.md
├── data/
│   ├── orders_etl.json
│   └── final_orders_etl.json
├── lambda/
│   └── lambda_handler.py
├── athena/
│   └── sample_queries.png
├── assets/
│   ├── screenshot_1.png
│   ├── screenshot_2.png
│   ├── screenshot_3.png
│   ├── screenshot_4.png
│   ├── screenshot_5.png
│   └── screenshot_6.png
```

## 💡 Key Features

- ✔️ Incremental Load Based on `order_date`
- ✔️ Flatten Nested JSON Using Python
- ✔️ Convert to Parquet for Performance
- ✔️ Use Glue Crawler to Detect Schema
- ✔️ Query Efficiently Using Athena

## 📬 Contact

**Author**: Umit Samanta  
**LinkedIn**: [linkedin.com/in/umitsamanta103](https://linkedin.com/in/umitsamanta103)  
**GitHub**: [github.com/umitsam14](https://github.com/umitsam14)

## 📌 License

This project is open-source and free to use under the MIT License.
