# Covid-19-Data-Analytics-Pipeline-AWS-Serverless-
 Designed and implemented a serverless data pipeline using Amazon S3, AWS Glue (PySpark
 ETL), and Amazon Redshift Serverless.

 # Project Overview
 This project demonstrates an end-to-end data engineering pipeline to ingest, process, and analyze COVID-19 data using AWS services. 

  # Key AWS Services:
   1.AWS S3-Storage for raw and processed data.

   2.AWS Glue crawler:AWS Glue Crawler scans raw data in S3 and creates/updates schema in the Glue Data Catalog.

   3.AWS Glue job:AWS Glue Jobs clean and transform the data:
         - Handle missing values
         - Standardize dates and country codes
         - Partition and store data in Parquet format

   4.AWS Redshift:The Glue job uploads the processed data into a Redshift table for deriving meaningful business insights.
     
 
