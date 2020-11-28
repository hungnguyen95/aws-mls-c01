# 1. SageMaker and Docker Containers

## SageMaker + Docker

- All models in SageMaker are hosted in Docker containers
    - Pre-built deep learning
    - Pre-built scikit-learn and Spark ML
    - Pre-built Tensorflow, MXNet, Chainer, PyTorch
        - Distributed training via Horovod or Parameter Servers
    - Your own training and inference code! Or extend a pre-built image.
- This allows you to use any script or algorithm within SageMaker, regardless of runtime or language
    - Containers are isolated, and contain all dependencies and resources needed to run

---

## Using Docker

- Docker containers are created from images
- Images are built from a Dockerfile
- Images are saved in a repository
    - Amazon Elastic ContainerRegistry

![1%20SageMaker%20and%20Docker%20Containers%20a4d0e74084624b2885be4cd0eb58ef1c/Untitled.png](1%20SageMaker%20and%20Docker%20Containers%20a4d0e74084624b2885be4cd0eb58ef1c/Untitled.png)

---

## Amazon SageMaker Containers

- Library for making containers compatible with SageMaker

    `RUN pip install sagemaker-containers` in your Dockerfile

---

## Structure of a training container

![1%20SageMaker%20and%20Docker%20Containers%20a4d0e74084624b2885be4cd0eb58ef1c/Untitled%201.png](1%20SageMaker%20and%20Docker%20Containers%20a4d0e74084624b2885be4cd0eb58ef1c/Untitled%201.png)

---

## Structure of a Deployment Container

![1%20SageMaker%20and%20Docker%20Containers%20a4d0e74084624b2885be4cd0eb58ef1c/Untitled%202.png](1%20SageMaker%20and%20Docker%20Containers%20a4d0e74084624b2885be4cd0eb58ef1c/Untitled%202.png)

---

## Structure of your Docker image

- WORKDIR
    - nginx.conf
    - predictor.py
    - serve/
    - train/
    - wsgi.py

---

## Assembling it all in a Dockerfile

```docker
FROM tensorflow/tensorflow:2.0.0a0

RUN pip install sagemaker-containers

# Copies the training code inside the container
COPY train.py /opt/ml/code/train.py

# Defines train.py as script entrypoint
ENV SAGEMAKER_PROGRAM train.py
```

---

## Environment variable

- SAGEMAKER_PROGRAM
    - Run a script inside /opt/ml/code
- SAGEMAKER_TRAINING_MODULE
- SAGEMAKER_SERVICE_MODULE
- SM_MODEL_DIR
- SM_CHANNELS / SM_CHANNEL_*
- SM_HPS / SM_HP_*
- SM_USER_ARGS
- …and many more

---

## Using your own image

- `cd dockerfile`
- `!docker build -t foo .`

```python
from sagemaker.estimator import Estimator

estimator = Estimator(image_name=‘foo',
							role='SageMakerRole',
							train_instance_count=1,
							train_instance_type='local')

estimator.fit()
```

---

## Production Variants

- You can test out multiple models on live traffic using Production Variants
    - Variant Weights tell SageMaker how to distribute traffic among them
    - So, you could roll out a new iteration of your model at say 10% variant weight
    - Once you’re confident in its performance, ramp it up to 100%
- This lets you do A/B tests, and to validate performance in real world settings
    - Offline validation isn’t always useful