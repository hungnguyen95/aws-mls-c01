# 8. L1 and L2 Regularization

## L1 and L2 Regularization

- Preventing overfitting in ML in general
- A regularization term is added as weights are learned
- L1 term is the sum of the weights:

    $\lambda \sum_{i=1}^k |w_i|$

- L2 term is the sum of the square of the weights

    $\lambda \sum_{i=1}^k w_i^2$

- Same idea can be applied to loss functions

![8%20L1%20and%20L2%20Regularization%20dd086c92cc204c218c36185d297a686a/Untitled.png](8%20L1%20and%20L2%20Regularization%20dd086c92cc204c218c36185d297a686a/Untitled.png)

---

## What’s the difference?

- L1: sum of weights
    - Performs feature selection – entire features go to 0
    - Computationally inefficient
    - Sparse output
- L2: sum of square of weights
    - All features remain considered, just weighted
    - Computationally efficient
    - Dense output

---

## Why would you want L1?

- Feature selection can reduce dimensionality
    - Out of 100 features, maybe only 10 end up with non-zero coefficients!
    - The resulting sparsity can make up for its computational inefficiency
- But, if you think all of your features are important, L2 is probably a better choice.