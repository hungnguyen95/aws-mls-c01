# 13. DMS - Database Migration Service

- Quickly and securely migrate databases to AWS, resilient, self healing
- The source database remains available during the migration
- Supports:
    - Homogeneous migrations: ex Oracle to Oracle
    - Heterogeneous migrations: ex Microsoft SQL Server to Aurora
- Continuous Data Replication using CDC
- You must create an EC2 instance to perform the replication tasks

![13%20DMS%20-%20Database%20Migration%20Service%2074c4bde8b59748fc8052405f3a84619f/Untitled.png](13%20DMS%20-%20Database%20Migration%20Service%2074c4bde8b59748fc8052405f3a84619f/Untitled.png)

---

## AWS DMS vs Glue

- Glue:
    - Glue ETL - Run Apache Spark code, Scala or Python based, focus on the ETL
    - Glue ETL - Do not worry about configuring or managing the resources
    - Data Catalog to make the data available to Athena or Redshift Spectrum
- DMS:
    - Continuous Data Replication
    - No data transformation
    - Once the data is in AWS, you can use Glue to transform it