# 1. Activation Functions

- Define the output of a node / neuron given its input signals

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled.png)

---

## Linear activation function

- It doesn’t really *do* anything
- Can’t do backpropagation

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%201.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%201.png)

---

## Binary step function

- It’s on or off
- Can’t handle multiple classification – it’s binary after all
- Vertical slopes don’t work well with calculus!

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%202.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%202.png)

---

## Instead we need non-linear activation functions

- These can create complex mappings between inputs and outputs
- Allow backpropagation (because they have a useful derivative)
- Allow for multiple layers (linear functions degenerate to a single layer)

---

## Sigmoid / Logistic / TanH

- Nice & smooth
- Scales everything from 0-1 (Sigmoid / Logistic) or -1 to 1 (tanh / hyperbolic tangent)
- But: changes slowly for high or low values
    - The “Vanishing Gradient” problem

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%203.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%203.png)

                    Sigmoid AKA Logistic

- Computationally expensive
- Tanh generally preferred over sigmoid

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%204.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%204.png)

            TanH AKA Hyperbolic Tangent

---

## Rectified Linear Unit (ReLU)

- Now we’re talking
- Very popular choice
- Easy & fast to compute
- But, when inputs are zero or negative, we have a linear function and all of its problems
    - The “Dying ReLU problem”

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%205.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%205.png)

---

## Leaky ReLU

- Solves “dying ReLU” by introducing a negative slope below 0 (usually not as steep as this)

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%206.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%206.png)

---

## Parametric ReLU (PReLU)

- ReLU, but the slope in the negative part is learned via backpropagation
- Complicated and YMMV

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%207.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%207.png)

---

## Other ReLU variants

- Exponential Linear Unit (ELU)
- Swish
    - From Google, performs really well
    - But it’s from Google, not Amazon…
    - Mostly a benefit with very deep networks (40+ layers)

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%208.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%208.png)

- Maxout
    - Outputs the max of the inputs
    - Technically ReLU is a special case of maxout
    - But doubles parameters that need to be trained, not often practical.

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%209.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%209.png)

---

## Softmax

- Used on the final output layer of a multiple classification problem
- Basically converts outputs to probabilities of each classification
- Can’t produce more than one label for something (sigmoid can)
- Don’t worry about the actual function for the exam, just know what it’s used for

![1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%2010.png](1%20Activation%20Functions%203deebb997b52458c9287711034542c8f/Untitled%2010.png)

---

## Choosing an activation function

- For multiple classification, use softmax on the output layer
- RNN’s do well with Tanh
- For everything else
    - Start with ReLU
    - If you need to do better, try Leaky ReLU
    - Last resort: PReLU, Maxout
    - Swish for really deep networks