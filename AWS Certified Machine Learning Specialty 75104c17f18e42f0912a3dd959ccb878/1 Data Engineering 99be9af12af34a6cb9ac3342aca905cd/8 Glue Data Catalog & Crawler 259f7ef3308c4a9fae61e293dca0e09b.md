# 8. Glue Data Catalog & Crawler

- Metadata repository for all your tables
    - Automated Schema Inference
    - Schemas are versioned
- Integrates with Athena or Redshift Spectrum (schema & data discovery)
- Glue Crawlers can help build the Glue Data Catalog

![8%20Glue%20Data%20Catalog%20&%20Crawler%20259f7ef3308c4a9fae61e293dca0e09b/Untitled.png](8%20Glue%20Data%20Catalog%20&%20Crawler%20259f7ef3308c4a9fae61e293dca0e09b/Untitled.png)

---

## Glue Data Catalog - Crawlers

- Crawlers go through your data to infer schemas and partitions
- Works JSON, Parquet, CSV, relational store
- Crawlers work for: S3, Amazon Redshift, Amazon RDS
- Run the Crawler on a Schedule or On Demand
- Need an IAM role / credentials to access the data stores

---

## Glue and S3 Partitions

- Glue crawler will extract partitions based on how your S3 data is organized
- Think up front about how you will be querying your data lake in S3
- Example: devices send sensor data every hour
- Do you query primarily by time ranges?
    - If so, organize your buckets as `s3://my-bucket/dataset/yyyy/mm/dd/device`
- Do you query primarily by device?
    - If so, organize your buckets as `s3://my-bucket/dataset/device/yyyy/mm/dd`

    ![8%20Glue%20Data%20Catalog%20&%20Crawler%20259f7ef3308c4a9fae61e293dca0e09b/Untitled%201.png](8%20Glue%20Data%20Catalog%20&%20Crawler%20259f7ef3308c4a9fae61e293dca0e09b/Untitled%201.png)