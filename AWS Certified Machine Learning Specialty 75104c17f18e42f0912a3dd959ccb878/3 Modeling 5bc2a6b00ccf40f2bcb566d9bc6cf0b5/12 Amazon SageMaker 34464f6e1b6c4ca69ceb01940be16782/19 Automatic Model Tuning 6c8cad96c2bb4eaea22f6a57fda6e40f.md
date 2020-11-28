# 19. Automatic Model Tuning

## Hyperparameter tuning

- How do you know the best values of learning rate, batch size, depth, etc?
- Often you have to experiment
- Problem blows up quickly when you have many different hyperparameters; need to try every

combination of every possible value somehow, train a model, and evaluate it every time

---

## Automatic Model Tuning

- Define the hyperparameters you care about and the ranges you want to try, and the metrics you are optimizing for
- SageMaker spins up a “HyperParameter Tuning Job” that trains as many combinations as you’ll allow
    - Training instances are spun up as needed, potentially a lot of them
- The set of hyperparameters producing the best results can then be deployed as a model
- It learns as it goes, so it doesn’t have to try every possible combination

---

## Automatic Model Tuning: Best Practices

- Don’t optimize too many hyperparameters at once
- Limit your ranges to as small a range as possible
- Use logarithmic scales when appropriate
- Don’t run too many training jobs concurrently
    - This limits how well the process can learn as it goes
- Make sure training jobs running on multiple instances report the correct objective metric in the end