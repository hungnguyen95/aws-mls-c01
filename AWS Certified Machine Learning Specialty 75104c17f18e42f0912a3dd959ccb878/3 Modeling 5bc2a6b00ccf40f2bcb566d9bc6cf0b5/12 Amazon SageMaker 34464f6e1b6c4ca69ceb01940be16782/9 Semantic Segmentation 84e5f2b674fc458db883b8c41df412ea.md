# 9. Semantic Segmentation

## Semantic Segmentation: What’s it for?

- Pixel-level object classification
- Different from image classification – that assigns labels to whole images
- Different from object detection – that assigns labels to bounding boxes
- Useful for self-driving vehicles, medical imaging diagnostics, robot sensing
- Produces a segmentation mask

---

## Semantic Segmentation: What training input does it expect?

- JPG Images and PNG annotations
- For both training and validation
- Label maps to describe annotations
- Augmented manifest image format supported for Pipe mode.
- JPG images accepted for inference

---

## Semantic Segmentation: How is it used?

- Built on MXNet Gluon and Gluon CV
- Choice of 3 algorithms:
    - Fully-Convolutional Network (FCN)
    - Pyramid Scene Parsing (PSP)
    - DeepLabV3
- Choice of backbones:
    - ResNet50
    - ResNet101
    - Both trained on ImageNet
- Incremental training, or training from scratch, supported too

---

## Semantic Segmentation: Important Hyperparameters

- Epochs, learning rate, batch size, optimizer, etc
- Algorithm
- Backbone

---

## Semantic Segmentation: Instance Types

- Only GPU supported for training (P2 or P3) on a single machine only
    - Specifically ml.p2.xlarge, ml.p2.8xlarge, ml.p2.16xlarge, ml.p3.2xlarge, ml.p3.8xlarge, or ml.p3.16xlarge
- Inference on CPU (C5 or M5) or GPU (P2 or P3)