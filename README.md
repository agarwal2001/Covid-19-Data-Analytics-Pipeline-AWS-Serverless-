# Covid-19-Data-Analytics-Pipeline-AWS-Serverless-
 Designed and implemented a serverless data pipeline using Amazon S3, AWS Glue (PySpark
 ETL), and Amazon Redshift Serverless.

 # Project Overview
 Raw CSVs are processed and loaded into Redshift, where aggregated queries can be run for insights like worldwide confirmed cases. 

  # Key AWS Services:
   1.AWS S3:
   * Created S3 buckets for raw and curated datasets.
   * Upload daily COVID CSV files into raw/.
   * Curated output written to s3://your-datalake-curated/covid/summary/.


   2.AWS Glue crawler:
   * Glue Crawler reads raw CSV files and infers schema.
   * Output catalog table: raw_covid_daily_reports.


   3.AWS Glue job: Glue Jobs clean and transform the data
   * Apply Mapping: normalize column names and types.
   * ResolveChoice: ensure numeric types.
   * Clean & Transform:
   * Parse Last Update → report_date
   * Standardize country and province names
   * Compute active_cases = confirmed - deaths - recovered
   * Filter invalid rows.
   * Aggregate by report_date & country_region.


   5.AWS Redshift:
   * Glue ETL reads Parquet from curated S3.
   * Applied Mapping to match Redshift schema.
   * Loaded data using JDBC connection (redshiftconnection4).
   * Data is efficiently loaded into Redshift with distribution and sort keys optimized for country and report date

     
 
