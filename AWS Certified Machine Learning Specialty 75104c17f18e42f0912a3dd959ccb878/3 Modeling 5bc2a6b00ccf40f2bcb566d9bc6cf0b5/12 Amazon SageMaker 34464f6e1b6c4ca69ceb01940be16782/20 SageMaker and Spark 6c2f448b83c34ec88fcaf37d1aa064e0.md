# 20. SageMaker and Spark

## Integrating SageMaker and Spark

- Pre-process data as normal with Spark
    - Generate DataFrames
- Use sagemaker-spark library
- SageMakerEstimator
    - KMeans, PCA, XGBoost
- SageMakerModel

![20%20SageMaker%20and%20Spark%206c2f448b83c34ec88fcaf37d1aa064e0/Untitled.png](20%20SageMaker%20and%20Spark%206c2f448b83c34ec88fcaf37d1aa064e0/Untitled.png)

---

## Integrating SageMaker and Spark

- Connect notebook to a remote EMR cluster running Spark (or use Zeppelin)
- Training dataframe should have:
    - A features column that is a vector of Doubles
    - An optional labels column of Doubles
- Call fit on your SageMakerEstimator to get a SageMakerModel
- Call transform on the SageMakerModel to make inferences
- Works with Spark Pipelines as well.

```python
val estimator = new KMeansSageMakerEstimator(
sagemakerRole = IAMRole(roleArn),
trainingInstanceType = "ml.p2.xlarge",
trainingInstanceCount = 1,
endpointInstanceType = "ml.c4.xlarge",
endpointInitialInstanceCount = 1)
.setK(10).setFeatureDim(784)
// train
val model = estimator.fit(trainingData)
val transformedData = model.transform(testData)
transformedData.show
```

---

## Why bother?

- Allows you to combine preprocessing big data in Spark with training and inference in SageMaker.

---

##