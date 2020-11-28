# 16. Factorization Machines

## Factorization Machines: What’s it for?

- Dealing with sparse data
    - Click prediction
    - Item recommendations
    - Since an individual user doesn’t interact with most pages / products the data is sparse
- Supervised
    - Classification or regression
- Limited to pair-wise interactions
    - User -> item for example

---

## Factorization Machines: What training input does it expect?

- recordIO-protobuf with Float32
    - Sparse data means CSV isn’t practical

---

## Factorization Machines: How is it used?

- Finds factors we can use to predict a classification (click or not? Purchase or not?) or value (predicted rating?) given a matrix representing some pair of things (users & items?)
- Usually used in the context of recommender systems

---

## Factorization Machines: Important Hyperparameters

- Initialization methods for bias, factors, and linear terms
    - Uniform, normal, or constant
    - Can tune properties of each method

---

## Factorization Machines: Instance Types

- CPU or GPU
    - CPU recommended
    - GPU only works with dense data