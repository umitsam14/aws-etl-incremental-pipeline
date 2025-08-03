# aws-etl-incremental-pipeline
A real-time serverless ETL pipeline on AWS to process and transform incoming JSON orders incrementally. The project flattens complex nested JSON using a Lambda function, writes the output to Parquet, triggers a Glue Crawler, and enables SQL querying in Athena.
