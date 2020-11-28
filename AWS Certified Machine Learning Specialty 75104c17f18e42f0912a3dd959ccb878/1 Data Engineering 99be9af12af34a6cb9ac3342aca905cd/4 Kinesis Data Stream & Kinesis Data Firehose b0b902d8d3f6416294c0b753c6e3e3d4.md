# 4. Kinesis Data Stream & Kinesis Data Firehose

## AWS Kinesis Overview

- Kinesis is a managed alternative to Apache Kafka
- Great for application logs, metrics, IoT, clickstreams
- Great for “real-time” big data
- Great for streaming processing frameworks (Spark, NiFi, etc…)
- Data is automatically replicated synchronously to 3 AZ

- **Kinesis Streams:** low latency streaming ingest at scale
- **Kinesis Analytics:** perform real-time analytics on streams using SQL
- **Kinesis Firehose:** load streams into S3, Redshift, ElasticSearch & Splunk
- **Kinesis Video Streams:** meant for streaming video in real-time

---

## Kinesis

![4%20Kinesis%20Data%20Stream%20&%20Kinesis%20Data%20Firehose%20b0b902d8d3f6416294c0b753c6e3e3d4/Untitled.png](4%20Kinesis%20Data%20Stream%20&%20Kinesis%20Data%20Firehose%20b0b902d8d3f6416294c0b753c6e3e3d4/Untitled.png)

---

## Kinesis Stream Overview

- Streams are divided in ordered Shards / Partitions

![4%20Kinesis%20Data%20Stream%20&%20Kinesis%20Data%20Firehose%20b0b902d8d3f6416294c0b753c6e3e3d4/Untitled%201.png](4%20Kinesis%20Data%20Stream%20&%20Kinesis%20Data%20Firehose%20b0b902d8d3f6416294c0b753c6e3e3d4/Untitled%201.png)

- **Shards have to be provisioned in advance (capacity planning)**
- Data retention is 24 hours by default, can go up to 7 days
- Ability to reprocess / replay data
- Multiple applications can consume the same stream
- Once data is inserted in Kinesis, it can’t be deleted (immutability)
- Records can be up to 1MB in size

---

## Kinesis Data Streams Limits to know

- Producer:
    - 1MB/s or 1000 messages/s at write PER SHARD
    - “ProvisionedThroughputException” otherwise
- Consumers
    - 2MB/s at read PER SHARD across all consumers
    - 5 API calls per second PER SHARD across all consumers
- Data Retention:
    - 24 hours data retention by default
    - Can be extended to 7 days

---

## Kinesis Data Firehose

- Fully Managed Service, no administration
- **Near Real Time** (60 seconds latency minimum for non full batches)
- **Data Ingestion into Redshift / Amazon S3 / ElasticSearch / Splunk**
- **Automatic scaling**
- Supports many data formats
- **Data Conversions from CSV / JSON to Parquet / ORC (only for S3)**
- Data Transformation through AWS Lambda (ex: CSV => JSON)
- Supports **compression** when target is Amazon S3 (GZIP, ZIP, and SNAPPY)
- Pay for the amount of data going through Firehose

---

## Kinesis Data Firehose Diagram

![4%20Kinesis%20Data%20Stream%20&%20Kinesis%20Data%20Firehose%20b0b902d8d3f6416294c0b753c6e3e3d4/Untitled%202.png](4%20Kinesis%20Data%20Stream%20&%20Kinesis%20Data%20Firehose%20b0b902d8d3f6416294c0b753c6e3e3d4/Untitled%202.png)

---

## Kinesis Data Firehose Delivery Diagram

![4%20Kinesis%20Data%20Stream%20&%20Kinesis%20Data%20Firehose%20b0b902d8d3f6416294c0b753c6e3e3d4/Untitled%203.png](4%20Kinesis%20Data%20Stream%20&%20Kinesis%20Data%20Firehose%20b0b902d8d3f6416294c0b753c6e3e3d4/Untitled%203.png)

---

## Kinesis Data Stream vs Firehose

- Stream
    - Going to write custom code (producer / consumer)
    - Real time (~200 ms latency for classic, ~70 ms latency for enhanced fan-out)
    - Must manage scaling (shard splitting / merging)
    - Data Storage for 1 to 7 days, replay capability, multi consumers

- Firehose
    - Fully managed, send to S3, Splunk, Redshift, ElasticSearch
    - Serverless data transformations with Lambda
    - Near real time (lowest buffer time is 1 minute)
    - Automated Scaling
    - No data storage