# 11. Imputing Missing Data

## Mean Replacement

- Replace missing values with the mean value from the rest of the column (columns, not rows! A column represents a single feature; it only makes sense to take the mean from other samples of the same feature.)
- Fast & easy, won’t affect mean or sample size of overall data set
- Median may be a better choice than mean when outliers are present
- But it’s generally pretty terrible.
    - Only works on column level, misses correlations between features
    - Can’t use on categorical features (imputing with most frequent value can work in this case, though)
    - Not very accurate

![11%20Imputing%20Missing%20Data%20a51b8439f96a4837afa5ab3a20c21be7/Untitled.png](11%20Imputing%20Missing%20Data%20a51b8439f96a4837afa5ab3a20c21be7/Untitled.png)

---

## Dropping

- If not many rows contain missing data…
    - …and dropping those rows doesn’t bias your data…
    - …and you don’t have a lot of time…
    - …maybe it’s a reasonable thing to do
- But, it’s never going to be the right answer for the “best” approach.
- Almost anything is better. Can you substitute another similar field perhaps? (i.e., review summary vs. full text)

![11%20Imputing%20Missing%20Data%20a51b8439f96a4837afa5ab3a20c21be7/Untitled%201.png](11%20Imputing%20Missing%20Data%20a51b8439f96a4837afa5ab3a20c21be7/Untitled%201.png)

---

## Machine Learning

- KNN: Find K “nearest” (most similar) rows and average their values
    - Assumes numerical data, not categorical
    - There are ways to handle categorical data (Hamming distance), but categorical data is probably better served by ↓
- Deep Learning
    - Build a machine learning model to impute data for your machine learning model!
    - Works well for categorical data. Really well. But it’s complicated
- Regression
    - Find linear or non-linear relationships between the missing feature and other features
    - Most advanced technique: MICE (Multiple Imputation by Chained Equations)

---

## Just Get More Data

- What’s better than imputing data? Getting more real data!
- Sometimes you just have to try harder or collect more data