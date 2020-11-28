# 2. Amazon S3 - Storage Tiers & Lifecycle Rules

# S3 Storage Tiers

- Amazon S3 Standard - General Purpose
- Amazon S3 Standard-Infrequent Access (IA)
- Amazon S3 One Zone-Infrequent Access
- Amazon S3 Intelligent Tiering
- Amazon Glacier

![2%20Amazon%20S3%20-%20Storage%20Tiers%20&%20Lifecycle%20Rules%2096beddf07a7042ec9cfc7edb8add28d5/Untitled.png](2%20Amazon%20S3%20-%20Storage%20Tiers%20&%20Lifecycle%20Rules%2096beddf07a7042ec9cfc7edb8add28d5/Untitled.png)

---

# S3 Lifecycle Rules

- Set of rules to move data between different tiers, to save storage cost
- Example: **General Purpose => Infrequent Access => Glacier**

- **Transition actions**: objects are transitioned to another storage class.
    - Move objects to Standard IA class 60 days after creation
    - And move to Glacier for archiving after 6 months
- **Expiration actions**: S3 deletes expired objects on our behalf
    - Access log files can be set to delete after a specified period of time