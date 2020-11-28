# 10. AWS Data Stores for Machine Learning

- Redshift:
    - Data Warehousing, SQL analytics (OLAP - Online analytical processing)
    - Load data from S3 to Redshift
    - Use Redshift Spectrum to query data directly in S3 (no loading)

![10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled.png](10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled.png)

---

- RDS, Aurora:
    - Relational Store, SQL (OLTP - Online Transaction Processing)
    - Must provision servers in advance

![10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%201.png](10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%201.png)

![10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%202.png](10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%202.png)

---

- DynamoDB:
    - NoSQL data store, serverless, provision read/write capacity
    - Useful to store a machine learning model served by your application

![10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%203.png](10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%203.png)

---

- S3:
    - Object storage
    - Serverless, infinite storage
    - Integration with most AWS Services

![10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%204.png](10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%204.png)

---

- ElasticSearch:
    - Indexing of data
    - Search amongst data points
    - Clickstream Analytics

![10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%205.png](10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%205.png)

---

- ElastiCache:
    - Caching mechanism
    - Not really used for Machine Learning

![10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%206.png](10%20AWS%20Data%20Stores%20for%20Machine%20Learning%20ba930a2eb6244e0ab0b8d0defdc6c7d1/Untitled%206.png)