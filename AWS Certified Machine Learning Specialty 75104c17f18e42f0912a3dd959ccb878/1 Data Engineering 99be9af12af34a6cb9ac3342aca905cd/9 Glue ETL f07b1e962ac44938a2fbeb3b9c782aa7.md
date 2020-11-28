# 9. Glue ETL

- Transform data, Clean Data, Enrich Data (before doing analysis)
    - Generate ETL code in Python or Scala, you can modify the code
    - Can provide your own Spark or PySpark scripts
    - Target can be S3, JDBC (RDS, Redshift), or in Glue Data Catalog
- Fully managed, cost effective, pay only for the resources consumed
- Jobs are run on a serverless Spark platform

- Glue Scheduler to schedule the jobs
- Glue Triggers to automate job runs based on “events”

---

## Glue ETL - Transformations

- Bundled Transformations:
    - DropFields, DropNullFields – remove (null) fields
    - Filter – specify a function to filter records
    - Join – to enrich data
    - Map - add fields, delete fields, perform external lookups
- Machine Learning Transformations:
    - **FindMatches ML**: identify duplicate or matching records in your dataset, even when the records do not have a common unique identifier and no fields match exactly.
- Format conversions: CSV, JSON, Avro, Parquet, ORC, XML
- Apache Spark transformations (example: K-Means)