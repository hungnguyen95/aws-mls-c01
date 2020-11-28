# 1. Linear Learner

## Linear Learner: What’s it for?

- Linear regression
    - Fit a line to your training data
    - Predications based on that line
- Can handle both regression (numeric) predictions and classification predictions
    - For classification, a linear threshold function is used.
    - Can do binary or multi-class

![1%20Linear%20Learner%201fe5ca6e96d744a2b675c75fae503baa/Untitled.png](1%20Linear%20Learner%201fe5ca6e96d744a2b675c75fae503baa/Untitled.png)

---

## Linear Learner: What training input does it expect?

- RecordIO-wrapped protobuf
    - Float32 data only!
- CSV
    - First column assumed to be the label
- File or Pipe mode both supported

---

## Linear Learner: How is it used?

- Preprocessing
    - Training data must be normalized (so all features are weighted the same)
    - Linear Learner can do this for you automatically
    - Input data should be shuffled
- Training
    - Uses stochastic gradient descent
    - Choose an optimization algorithm (Adam, AdaGrad, SGD, etc)
    - Multiple models are optimized in parallel
    - Tune L1, L2 regularization
- Validation
    - Most optimal model is selected

---

## Linear Learner: Important Hyperparameters

- Balance_multiclass_weights
    - Gives each class equal importance in loss functions
- Learning_rate, mini_batch_size
- L1
    - Regularization
- Wd
    - Weight decay (L2 regularization)

---

## Linear Learner: Instance Types

- Training
    - Single or multi-machine CPU or GPU
    - Multi-GPU does not help