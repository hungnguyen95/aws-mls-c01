# 3. SageMaker Security

## General AWS Security

- Use Identity and Access Management (IAM)
    - Set up user accounts with only the permissions they need
- Use MFA
- Use SSL/TLS when connecting to anything
- Use CloudTrail to log API and user activity
- Use encryption
- Be careful with PII

---

## Protecting your Data at Rest in SageMaker

- AWS Key Management Service (KMS)
    - Accepted by notebooks and all SageMaker jobs
        - Training, tuning, batch transform, endpoints
        - Notebooks and everything under `/opt/ml/` and `/tmp` can be encrypted with a KMS key
- S3
    - Can use encrypted S3 buckets for training data and hosting models
    - S3 can also use KMS

---

## Protecting Data in Transit in SageMaker

- All traffic supports TLS / SSL
- IAM roles are assigned to SageMaker to give it permissions to access resources
- Inter-node training communication may be optionally encrypted
    - Can increase training time and cost with deep learning
    - AKA inter-container traffic encryption
    - Enabled via console or API when setting up a training or tuning job