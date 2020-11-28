# 21. New SageMaker Features

## SageMaker Studio

- Visual IDE for machine learning!
- Integrates many of the features we’re about to cover.

![21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled.png](21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled.png)

---

## SageMaker Notebooks

- Create and share Jupyter notebooks with SageMaker Studio
- Switch between hardware configurations (no infrastructure to manage)

![21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%201.png](21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%201.png)

---

## SageMaker Experiments

- Organize, capture, compare, and search your ML jobs

![21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%202.png](21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%202.png)

---

## SageMaker Debugger

- Saves internal model state at periodical intervals
    - Gradients / tensors over time as a model is trained
    - Define rules for detecting unwanted conditions while training
    - A debug job is run for each rule you configure
    - Logs & fires a CloudWatch event when the rule is hit

---

## SageMaker Autopilot

- Automates:
    - Algorithm selection
    - Data preprocessing
    - Model tuning
    - All infrastructure
- It does all the trial & error for you
- More broadly this is called AutoML

![21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%203.png](21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%203.png)

---

## SageMaker Model Monitor

- Get alerts on quality deviations on your deployed models
- Visualize data drift
    - Example: loan model starts giving people more credit due to drifting or missing input features
- No code needed

![21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%204.png](21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%204.png)

---

## Putting them together

![21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%205.png](21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78/Untitled%205.png)