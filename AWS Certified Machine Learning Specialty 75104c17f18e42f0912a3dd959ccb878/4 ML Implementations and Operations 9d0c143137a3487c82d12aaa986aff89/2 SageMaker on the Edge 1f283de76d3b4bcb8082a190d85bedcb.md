# 2. SageMaker on the Edge

## SageMaker Neo

- Train once, run anywhere
    - Edge devices
        - ARM, Intel, Nvidia processors
        - Embedded in whatever – your car?
- Optimizes code for specific devices
    - Tensorflow, MXNet, PyTorch,ONNX, XGBoost
- Consists of a **compiler** and a **runtime**

---

## Neo + AWS IoT Greengrass

- Neo-compiled models can be deployed to an HTTPS endpoint
    - Hosted on C5, M5, M4, P3, or P2 instances
    - Must be same instance type used for compilation
- OR! You can deploy to IoT Greengrass
    - This is how you get the model to an actual edge device
    - Inference at the edge with local data, using model trained in the cloud
    - Uses Lambda inference applications