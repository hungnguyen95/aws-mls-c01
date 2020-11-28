# 8. Image Classification

- Assign one or more labels to an image
- Doesn’t tell you where objects are, just what objects are in the image

---

## Image Classification: What training input does it expect?

- Apache MXNet RecordIO
    - Not protobuf!
    - This is for interoperability with other deep learning frameworks.
- Or, raw jpg or png images
- Image format requires .lst files to associate image index, class label, and path to the image
- Augmented Manifest Image Format enables Pipe mode

```json
5 1 your_image_directory/train_img_dog1.jpg
1000 0 your_image_directory/train_img_cat1.jpg
22 1 your_image_directory/train_img_dog2.jpg

{"source-ref":"s3://image/filename1.jpg", "class":"0"}
{"source-ref":"s3://image/filename2.jpg", "class":"1", "class-metadata": {"class-name": "cat", "type" : "groundtruth/imageclassification"}}
```

---

## Image Classification: How is it used?

- ResNet CNN under the hood
- Full training mode
    - Network initialized with random weights
- Transfer learning mode
    - Initialized with pre-trained weights
    - The top fully-connected layer is initialized with random weights
- Network is fine-tuned with new training data
- Default image size is 3-channel 224x224 (ImageNet’s dataset)

---

## Image Classification: Important Hyperparameters

- The usual suspects for deep learning
    - Batch size, learning rate, optimizer
- Optimizer-specific parameters
    - Weight decay, beta 1, beta 2, eps,gamma

---

## Image Classification: Instance Types

- GPU instances for training (P2, P3) Multi-GPU and multi-machine OK.
- CPU or GPU for inference (C4, P2, P3)