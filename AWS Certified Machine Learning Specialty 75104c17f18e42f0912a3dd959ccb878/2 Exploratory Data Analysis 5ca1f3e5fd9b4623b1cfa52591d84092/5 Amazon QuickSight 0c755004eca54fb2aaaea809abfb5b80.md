# 5. Amazon QuickSight

## What is QuickSight?

- Fast, easy, cloud-powered business analytics service
- Allows all employees in an organization to:
    - Build visualizations
    - Perform ad-hoc analysis
    - Quickly get business insights from data
    - Anytime, on any device (browsers, mobile)
- Serverless

---

## QuickSight Data Sources

- Redshift
- Aurora / RDS
- Athena
- EC2-hosted databases
- Files (S3 or on-premises)
    - Excel
    - CSV, TSV
    - Common or extended log format
- Data preparation allows limited ETL

---

## SPICE

- Data sets are imported into SPICE
    - Super-fast, Parallel, In-memory Calculation Engine
    - Uses columnar storage, in-memory, machine code generation
    - Accelerates interactive queries on large datasets
- Each user gets 10GB of SPICE
- Highly available / durable
- Scales to hundreds of thousands of users

---

## QuickSight Use Cases

- Interactive ad-hoc exploration / visualization of data
- Dashboards and KPI’s
- Stories
    - Guided tours through specific views of an analysis
    - Convey key points, thought process, evolution of an analysis
- Analyze / visualize data from:
    - Logs in S3
    - On-premise databases
    - AWS (RDS, Redshift, Athena, S3)
    - SaaS applications, such as Salesforce
    - Any JDBC/ODBC data source

---

## Machine Learning Insights

- Anomaly detection
- Forecasting
- Auto-narratives

---

## QuickSight Anti-Patterns

- Highly formatted canned reports
    - QuickSight is for ad-hoc queries, analysis, and visualization
- ETL
    - Use Glue instead, although QuickSight can do some transformations

---

## QuickSight Security

- Multi-factor authentication on your account
- VPC connectivity
    - Add QuickSight’s IP address range to your database security groups
- Row-level security
- Private VPC access
    - Elastic Network Interface, AWS Direct Connect

---

## QuickSight User Management

- Users defined via IAM, or email signup
- Active Directory integration with QuickSight Enterprise Edition

---

## QuickSight Pricing

- Annual subscription
    - Standard: $9 / user /month
    - Enterprise: $18 / user / month
- Extra SPICE capacity (beyond 10GB)
    - $0.25 (standard) $0.38 (enterprise) / GB / month
- Month to month
    - **Standard: $12 / GB / month**
    - **Enterprise: $24 / GB / month**
- Enterprise edition
    - Encryption at rest
    - Microsoft Active Directory integration