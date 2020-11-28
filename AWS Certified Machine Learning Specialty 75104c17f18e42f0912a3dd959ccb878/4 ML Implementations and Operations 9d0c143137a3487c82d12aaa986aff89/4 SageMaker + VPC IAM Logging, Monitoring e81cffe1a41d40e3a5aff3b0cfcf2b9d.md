# 4. SageMaker + VPC/IAM/Logging, Monitoring

## SageMaker + VPC

- Training jobs run in a Virtual Private Cloud (VPC)
- You can use a private VPC for even more security
    - You’ll need to set up S3 VPC endpoints
    - Custom endpoint policies and S3 bucket policies can keep this secure
- Notebooks are Internet-enabled by default
    - This can be a security hole
    - If disabled, your VPC needs an interface endpoint (PrivateLink) or NAT Gateway, and allow  outbound connections, for training and hosting to work
- Training and Inference Containers are also Internet-enabled by default
    - Network isolation is an option, but this also prevents S3 access

---

## SageMaker + IAM

- User permissions for:
    - CreateTrainingJob
    - CreateModel
    - CreateEndpointConfig
    - CreateTransformJob
    - CreateHyperParameterTuningJob
    - CreateNotebookInstance
    - UpdateNotebookInstance
- Predefined policies:
    - AmazonSageMakerReadOnly
    - AmazonSageMakerFullAccess
    - AdministratorAccess
    - DataScientist

---

## SageMaker Logging and Monitoring

- CloudWatch can log, monitor and alarm on:
    - Invocations and latency of endpoints
    - Health of instance nodes (CPU, memory, etc)
    - Ground Truth (active workers, how much they are doing)
- CloudTrail records actions from users, roles, and services within SageMaker
    - Log files delivered to S3 for auditing