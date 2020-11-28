# 2. XGBoost

## XGBoost: What’s it for?

- eXtreme Gradient Boosting
    - Boosted group of decision trees
    - New trees made to correct the errors of previous trees
    - Uses gradient descent to minimize loss as new trees are added
- It’s been winning a lot of Kaggle competitions
    - And it’s fast, too
- Can be used for classification
- And also for regression
    - Using regression trees

---

## XGBoost: What training input does it expect?

- XGBoost is weird, since it’s not made for SageMaker. It’s just open source XGBoost
- So, it takes CSV or libsvm input.
- AWS recently extended it to accept recordIO-protobuf and Parquet as well.

---

## XGBoost: How is it used?

- Models are serialized/deserialized with Pickle
- Can use as a framework within notebooks
- Sagemaker.xgboost
- Or as a built-in SageMaker algorithm

---

## XGBoost: Important Hyperparameters

- There are a lot of them. A few:
- Subsample
    - Prevents overfitting
- Eta
    - Step size shrinkage, prevents overfitting
- Gamma
    - Minimum loss reduction to create a partition; larger = more conservative
- Alpha
    - L1 regularization term; larger = more conservative
- Lambda
    - L2 regularization term; larger = more conservative

---

## XGBoost: Instance Types

- Uses CPU’s only
- Is memory-bound, not computebound
- So, M4 is a good choice