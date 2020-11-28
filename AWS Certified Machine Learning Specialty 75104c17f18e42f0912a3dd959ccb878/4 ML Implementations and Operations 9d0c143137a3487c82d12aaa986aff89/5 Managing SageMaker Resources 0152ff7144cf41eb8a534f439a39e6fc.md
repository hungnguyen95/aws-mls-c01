# 5. Managing SageMaker Resources

## Choosing your instance types

- We covered this under “modeling”, even though it’s an operations concern
- In general, algorithms that rely on deep learning will benefit from GPU instances (P2 or P3) for training
- Inference is usually less demanding and you can often get away with compute instances there (C4, C5)
- GPU instances can be really pricey

---

## Managed Spot Training

- Can use EC2 Spot instances for training
    - Save up to 90% over on-demand instances
- Spot instances can be interrupted!
    - Use checkpoints to S3 so training can resume
- Can increase training time as you need to wait for spot instances to become available

---

## Elastic Inference

- Accelerates deep learning inference
    - At fraction of cost of using a GPU instance for inference
- EI accelerators may be added alongside a CPU instance
    - ml.eia1.medium / large / xlarge
- EI accelerators may also be applied to notebooks
- Works with Tensorflow and MXNet pre-built containers
    - ONNX may be used to export models to MXNet
- Works with custom containers built with EI enabled Tensorflow or MXNet
- Works with Image Classification and Object Detection built-in algorithms

---

## Automatic Scaling

- You set up a scaling policy to define target metrics, min/max capacity, cooldown periods
- Works with CloudWatch
- Dynamically adjusts number of instances for a production variant
- Load test your configuration before using it!

---

## SageMaker and Availability Zones

- SageMaker automatically attempts to distribute instances across availability zones
- But you need more than one instance for this to work!
- Deploy multiple instances for each production endpoint
- Configure VPC’s with at least two subnets, each in a different AZ