# 11. AWS Data Pipeline Features

- Destinations include S3, RDS, DynamoDB, Redshift and EMR
- Manages task dependencies
- Retries and notifies on failures
- Data sources may be on-premises
- Highly available

![11%20AWS%20Data%20Pipeline%20Features%2001ad89061992479fb5b84b456530f99f/Untitled.png](11%20AWS%20Data%20Pipeline%20Features%2001ad89061992479fb5b84b456530f99f/Untitled.png)

---

## AWS Data Pipeline vs Glue

- Glue:
    - Glue ETL - Run Apache Spark code, Scala or Python based, focus on the ETL
    - Glue ETL - Do not worry about configuring or managing the resources
    - Data Catalog to make the data available to Athena or Redshift Spectrum
- Data Pipeline:
    - Orchestration service
    - More control over the environment, compute resources that run code, & code
    - Allows access to EC2 or EMR instances (creates resources in your own account)