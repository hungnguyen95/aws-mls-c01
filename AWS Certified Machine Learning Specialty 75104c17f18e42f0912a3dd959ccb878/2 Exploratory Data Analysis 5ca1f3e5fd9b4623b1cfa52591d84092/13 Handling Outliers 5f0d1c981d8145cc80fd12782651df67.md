# 13. Handling Outliers

## Variance measures how “spread-out” the data is

- Variance $\sigma^2$ is simply the average of the squared differences from the mean
- Example: What is the variance of the data set (1, 4, 5, 4, 8)?
    - First find the mean: (1+4+5+4+8)/5 = 4.4
    - Now find the differences from the mean: (-3.4, -0.4, 0.6, -0.4, 3.6)
    - Find the squared differences: (11.56, 0.16, 0.36, 0.16, 12.96)
    - Find the average of the squared differences:
    - $\sigma^2$ = (11.56 + 0.16 + 0.36 + 0.16 + 12.96) / 5 = 5.04

---

## Standard Deviation 𝜎 is just the square root of the variance

$\sigma^2$ = 5.04

$\sigma$ = $\sqrt{5.04}$ = 2.24

So the standard deviation of (1, 4, 5, 4, 8) is 2.24.

This is usually used as a way to identify outliers. Data points that lie more than one std from the mean can be considered as unusal

You can talk about how extreme a data point is by talking about “how many sigmas $\sigma$” away from the mean it is

---

## Dealing with Outliers

- Sometimes it’s appropriate to remove outliers from your training data
- Do this responsibly! Understand why you are doing this.
- For example: in collaborative filtering, a single user who rates thousands of movies could have a big effect on everyone else’s ratings. That may not be desirable.
- Another example: in web log data, outliers may represent bots or other agents that should be

discarded.

- But if someone really wants the mean income of US citizens for example, don’t toss out billionaires just because you want to

---

## Dealing with Outliers

- Our old friend standard deviation provides a principled way to classify outliers.
- Find data points more than some multiple of a standard deviation in your training data.
- What multiple? You just have to use common sense.
- Remember AWS’s Random Cut Forest algorithm creeps into many of its services – it is made for outlier detection
    - Found within QuickSight, Kinesis Analytics, SageMaker, and more

---

## Example: Income Inequality

![13%20Handling%20Outliers%205f0d1c981d8145cc80fd12782651df67/Untitled.png](13%20Handling%20Outliers%205f0d1c981d8145cc80fd12782651df67/Untitled.png)

![13%20Handling%20Outliers%205f0d1c981d8145cc80fd12782651df67/Untitled%201.png](13%20Handling%20Outliers%205f0d1c981d8145cc80fd12782651df67/Untitled%201.png)