# 7. EMR and Hadoop Overview

## What is EMR?

- Elastic MapReduce
- Managed Hadoop framework on EC2 instances
- Includes Spark, HBase, Presto, Flink, Hive & more
- EMR Notebooks
- Several integration points with AWS

---

## An EMR Cluster

- Master node: manages the cluster
    - Single EC2 instance
- Core node: Hosts HDFS data and runs tasks
    - Can be scaled up & down, but with some risk
- Task node: Runs tasks, does not host data
    - No risk of data loss when removing
    - Good use of spot instances

![7%20EMR%20and%20Hadoop%20Overview%2006348c972f8046dda568a612864071ad/Untitled.png](7%20EMR%20and%20Hadoop%20Overview%2006348c972f8046dda568a612864071ad/Untitled.png)

---

## EMR Usage

- Transient vs Long-Running Clusters
    - Can spin up task nodes using Spot instances for temporary capacity
    - Can use reserved instances on long-running clusters to save $
- Connect directly to master to run jobs
- Submit ordered steps via the console

---

## EMR / AWS Integration

- Amazon EC2 for the instances that comprise the nodes in the cluster
- Amazon VPC to configure the virtual network in which you launch your instances
- Amazon S3 to store input and output data
- Amazon CloudWatch to monitor cluster performance and configure alarms
- AWS IAM to configure permissions
- AWS CloudTrail to audit requests made to the service
- AWS Data Pipeline to schedule and start your clusters

---

## EMR Storage

- HDFS
- EMRFS: access S3 as if it were HDFS
    - EMRFS Consistent View – Optional for S3 consistency
    - Uses DynamoDB to track consistency
- Local file system
- EBS for HDFS

---

## EMR promises

- EMR charges by the hour
    - Plus EC2 charges
- Provisions new nodes if a core node fails
- Can add and remove tasks nodes on the fly
- Can resize a running cluster’s core nodes