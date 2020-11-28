# 6. Inference Pipelines

- Linear sequence of 2-5 containers
- Any combination of pre-trained built-in algorithms or your own algorithms in Docker containers
- Combine pre-processing, predictions, post-processing
- Spark ML and scikit-learn containers OK
    - Spark ML can be run with Glue or EMR
    - Serialized into MLeap format
- Can handle both real-time inference and batch transforms