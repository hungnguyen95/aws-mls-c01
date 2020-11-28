# 6. Regularization Techniques

## What is regularization?

- Preventing overfitting
    - Models that are good at making predictions on the data they were trained on, but not on new data it hasn’t seen before
    - Overfitted models have learned patterns in the training data that don’t generalize to the real world
    - Often seen as high accuracy on training data set, but lower accuracy on test or evaluation data set.
        - When training and evaluating a model, we use training, evaluation, and testing data sets.
- Regularization techniques are intended to prevent overfitting.

---

## Dropout

![6%20Regularization%20Techniques%20d7acbc6d923a44a18667259c5d463408/Untitled.png](6%20Regularization%20Techniques%20d7acbc6d923a44a18667259c5d463408/Untitled.png)

---

## Early Stopping

![6%20Regularization%20Techniques%20d7acbc6d923a44a18667259c5d463408/Untitled%201.png](6%20Regularization%20Techniques%20d7acbc6d923a44a18667259c5d463408/Untitled%201.png)

- When val_acc is stable but train_acc continue to increasing, we can use early stop technical
- It prevents over fitting on your dataset