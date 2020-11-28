# 7. Vanishing & Exploding Gradient

## The Vanishing Gradient Problem

- When the slope of the learning curve approaches zero, things can get stuck
- We end up working with very small numbers that slow down training, or even introduce numerical errors
- Becomes a problem with deeper networks and RNN’s as these “vanishing gradients” propagate to deeper layers
- Opposite problem: “exploding gradients

![7%20Vanishing%20&%20Exploding%20Gradient%20d3b081b038ad488abe063af6e68b4bf1/Untitled.png](7%20Vanishing%20&%20Exploding%20Gradient%20d3b081b038ad488abe063af6e68b4bf1/Untitled.png)

---

## Fixing the Vanishing Gradient Problem

- Multi-level heirarchy
    - Break up levels into their own sub-networks trained individually
- Long short-term memory (LSTM)
- Residual Networks
    - i.e., ResNetEnsemble of shorter networks
- Better choice of activation function
    - ReLU is a good choice

---

## Gradient Checking

- A debugging technique
- Numerically check the derivatives computed during training
- Useful for validating code of neural network training
    - But you’re probably not going to be writing this code…