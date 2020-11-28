# 9. EMR Notebooks, Security and Instance Types

## EMR Notebook

- Similar concept to Zeppelin, with more AWS integration
- Notebooks backed up to S3
- Provision clusters from the notebook!
- Hosted inside a VPC
- Accessed only via AWS console

![9%20EMR%20Notebooks,%20Security%20and%20Instance%20Types%20dd41fa37e7f5421a8960820657625eed/Untitled.png](9%20EMR%20Notebooks,%20Security%20and%20Instance%20Types%20dd41fa37e7f5421a8960820657625eed/Untitled.png)

---

## EMR Security

- IAM policies
- Kerberos
- SSH
- IAM roles

---

## EMR: Choosing Instance Types

- Master node:
    - m4.large if < 50 nodes, m4.xlarge if > 50 nodes
- Core & task nodes:
    - m4.large is usually good
    - If cluster waits a lot on external dependencies (i.e. a web crawler), t2.medium
    - Improved performance: m4.xlarge
    - Computation-intensive applications: high CPU instances
    - Database, memory-caching applications: high memory instances
    - Network / CPU-intensive (NLP, ML) – cluster computer instances
- Spot instances
    - Good choice for task nodes
    - Only use on core & master if you’re testing or very cost-sensitive; you’re risking partial data loss