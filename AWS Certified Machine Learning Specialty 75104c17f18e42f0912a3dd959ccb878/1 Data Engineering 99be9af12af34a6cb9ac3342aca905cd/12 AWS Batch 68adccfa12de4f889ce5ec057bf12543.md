# 12. AWS Batch

- Run batch jobs as Docker images
- Dynamic provisioning of the instances (EC2 & Spot Instances)
- Optimal quantity and type based on volume and requirements
- No need to manage clusters, fully serverless
- You just pay for the underlying EC2 instances
- Schedule Batch Jobs using CloudWatch Events
- Orchestrate Batch Jobs using AWS Step Functions

---

## AWS Batch vs Glue

- Glue:
    - Glue ETL - Run Apache Spark code, Scala or Python based, focus on the ETL
    - Glue ETL - Do not worry about configuring or managing the resources
    - Data Catalog to make the data available to Athena or Redshift Spectrum

- Batch:
    - For any computing job regardless of the job (must provide Docker image)
    - Resources are created in your account, managed by Batch
    - For any non-ETL related work, Batch is probably better