# Analytics

# Athena

- Used to query data in S3 using SQL queries

- Interactive query service for analyzing data in Amazon S3 using SQL
- Serverless; no need to manage infrastructure
- Works with data formats like CSV, JSON, Parquet, and ORC
- Integration with AWS Glue for data cataloging and schema discovery

# Kinesis Family

- Used for stream or real-time processing of data (such as stock prices or video streaming)

- Real-time data streaming and analytics platform
- Captures, processes, and stores streaming data
- Loads streaming data into data lakes, warehouses, or analytics tools like Redshift and S3
- Processes real-time streams using SQL queries

# Quicksight

- Used for business intelligence/analytics to visualize your data using reports and dashboard

- Cloud-native business intelligence tool for data visualization and reporting
- Supports interactive dashboards, machine learning insights, and collaboration
- Directly integrates with AWS data sources like Redshift, Athena, and S3
- Supports pay-per-session pricing for cost efficiency

# Amazon Redshift

- Fully managed data warehouse optimized for large-scale analytics
- Columnar storage and advanced compression for high query performance
- Integrates with S3 for data lake querying using Redshift Spectrum

# AWS Glue

- Serverless data integration and ETL (extract, transform, load) service
- Manages metadata with a central data catalog
- Auto-generates ETL scripts and supports Python and Scala

# AWS Lake Formation

- Simplifies the creation of secure data lakes
- Automates data ingestion, transformation, and security policy application
- Integrates with S3 and other analytics services like Athena and Redshift

# EMR (Elastic MapReduce)

- A hosted hadoop framework that also supports Spark, Hive and Presto

- Managed service for big data processing using frameworks like Apache Spark, Hadoop, and Presto
- Scales to process petabytes of data
- Cost-effective with spot instances and auto-scaling

# Amazon OpenSearch Service

- Managed service for search, log analytics, and real-time monitoring
- Fully integrates with Kinesis, CloudWatch, and Lambda
- Formerly known as Amazon Elasticsearch Service

# AWS Data Pipeline

- Workflow orchestration for data movement and transformation
- Automates ETL processes and integrates with various AWS services like S3, Redshift, and DynamoDB

# AWS Step Functions

- Coordinates distributed applications and analytics workflows
- Used to orchestrate analytics jobs across services like Glue, Lambda, and EMR

- 
