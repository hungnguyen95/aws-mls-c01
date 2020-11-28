# 4. Amazon Athena

## What is Athena?

- Interactive query service for S3 (SQL)
    - No need to load data, it stays in S3
- Presto under the hood (Presto underlying platform)
- Serverless!
- Supports many data formats
    - CSV (human readable)
    - JSON (human readable)
    - ORC (columnar, splittable)
    - Parquet (columnar, splittable)
    - Avro (splittable)
- Unstructured, semi-structured, or structured

---

## Some examples

- Ad-hoc queries of web logs
- Querying staging data before loading to Redshift
- Analyze CloudTrail / CloudFront / VPC / ELB etc logs in S3
- Integration with Jupyter, Zeppelin, RStudio notebooks
- Integration with QuickSight
- Integration via ODBC / JDBC with other visualization tools

---

## Athena + Glue

![4%20Amazon%20Athena%20e4e981fd6cfb4af191793c403c696770/Untitled.png](4%20Amazon%20Athena%20e4e981fd6cfb4af191793c403c696770/Untitled.png)

---

## Athena cost model

- Pay-as-you-go
    - $5 per TB scanned
    - Successful or cancelled queries count, failed queries do not.
    - No charge for DDL (CREATE/ALTER/DROP etc.)
- Save LOTS of money by using columnar formats
    - ORC, Parquet
    - Save 30-90%, and get better performance
- Glue and S3 have their own charges

---

## Athena Security

- Access control
    - IAM, ACLs, S3 bucket policies
    - AmazonAthenaFullAccess / AWSQuicksightAthenaAccess
- Encrypt results at rest in S3 staging directory
    - Server-side encryption with S3-managed key (SSE-S3)
    - Server-side encryption with KMS key (SSE-KMS)
    - Client-side encryption with KMS key (CSE-KMS)
- Cross-account access in S3 bucket policy possible
- Transport Layer Security (TLS) encrypts in-transit (between Athena and S3)

---

## Athena anti-patterns

- Highly formatted reports / visualization
    - That’s what QuickSight is for
- ETL
    - Use Glue instead