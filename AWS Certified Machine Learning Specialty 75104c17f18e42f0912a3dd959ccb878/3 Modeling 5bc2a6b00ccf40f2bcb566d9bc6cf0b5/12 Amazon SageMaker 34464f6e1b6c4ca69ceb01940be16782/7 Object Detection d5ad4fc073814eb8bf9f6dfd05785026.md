# 7. Object Detection

## Object Detection: What’s it for?

- Identify all objects in an image with bounding boxes
- Detects and classifies objects with a single deep neural network
- Classes are accompanied by confidence scores
- Can train from scratch, or use pretrained models based on ImageNet

---

## Object Detection: What training input does it expect?

- RecordIO or image format (jpg or png)
- With image format, supply a JSON file for annotation data for each image

```json
{
	"file": "your_image_directory/sample_image1.jpg",
	"image_size": [
		{
			"width": 500,
			"height": 400,
			"depth": 3
		}
	],
	"annotations": [
		{
			"class_id": 0,
			"left": 111,
			"top": 134,
			"width": 61,
			"height": 128
		},
	],
	"categories": [
		{
			"class_id": 0,
			"name": "dog"
		},
	]
}
```

---

## Object Detection: How is it used?

- Takes an image as input, outputs all instances of objects in the image with categories and confidence scores
- Uses a CNN with the Single Shot multibox Detector (SSD) algorithm
- The base CNN can be VGG-16 or ResNet-50
- Transfer learning mode / incremental training
- Use a pre-trained model for the base network weights, instead of random initial weights
- Uses flip, rescale, and jitter internally to avoid overfitting

---

## Object Detection: Important Hyperparameters

- Mini_batch_size
- Learning_rate
- Optimizer
    - Sgd, adam, rmsprop, adadelta

---

## Object Detection: Instance Types

- Use GPU instances for training (multi-GPU and multi-machine OK)
    - Ml.p2.xlarge, ml.p2.8xlarge, ml.p2.16xlarge, ml.p3.2xlarge, ml.p3.8clarge, ml.p3.16xlarge
- Use CPU or CPU for inference
    - C5, M5, P2, P3 all OK