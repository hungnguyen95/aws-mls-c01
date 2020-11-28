# 11. Ensemble Learning: Boosting & Bagging

## Ensemble methods

- Decision trees are prone to overfitting
- So, make lots of decision trees and let them all vote on the result
- This is a random forest
- How do they differ?

![11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled.png](11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled.png)

![11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled%201.png](11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled%201.png)

![11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled%202.png](11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled%202.png)

---

## Bagging

- Generate N new training sets by **random sampling with replacement**
- Each resampled model can be trained in parallel

![11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled%203.png](11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled%203.png)

---

## Boosting

- Observations are weighted
- Some will take part in new training sets more often
- Training is sequential; each classifier takes into account the previous one’s success

![11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled%204.png](11%20Ensemble%20Learning%20Boosting%20&%20Bagging%207583b9c92a4b4feab5d03d736908d2d5/Untitled%204.png)

---

## Bagging vs. Boosting

- XGBoost is the latest hotness
- Boosting generally yields better accuracy
- But bagging avoids overfitting
- Bagging is easier to parallelize
- So, depends on your goal