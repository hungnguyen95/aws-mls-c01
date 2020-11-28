# 12. Amazon SageMaker

## SageMaker is built to handle the entire machine learning workflow

![12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/Untitled.png](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/Untitled.png)

---

## SageMaker Training & Deployment

![12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/Untitled%201.png](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/Untitled%201.png)

---

## SageMaker Notebooks can direct the process

- Notebook Instances on EC2 are spun up from the console
    - S3 data access
    - Scikit_learn, Spark, Tensorflow
    - Wide variety of built-in models
    - Ability to spin up traininginstances
    - Abilty to deploy trained models for making predictions at scale

---

## Data prep on SageMaker

- Data must come from S3
    - Ideal format varies with algorithm –often it is RecordIO / Protobuf
- Apache Spark integrates with SageMaker
    - More on this later…
- Scikit_learn, numpy, pandas all at your disposal within a notebook

---

## Training on SageMaker

- Create a training job
    - URL of S3 bucket with training data
    - ML compute resources
    - URL of S3 bucket for output
    - ECR path to training code
- Training options
    - Built-in training algorithms
    - Spark MLLib
    - Custom Python Tensorflow / MXNet code
    - Your own Docker image
    - Algorithm purchased from AWS marketplace

---

## Deploying Trained Models

- Save your trained model to S3
- Can deploy two ways:
    - Persistent endpoint for making individual predictions on demand
    - SageMaker Batch Transform to get predictions for an entire dataset
- Lots of cool options
    - Inference Pipelines for more complex processing
    - SageMaker Neo for deploying to edge devices Elastic Inference for accelerating deep learning models
    - Automatic scaling (increase # of endpoints as needed)

---

## Built-in Algorithm in SageMaker

[1. Linear Learner](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/1%20Linear%20Learner%201fe5ca6e96d744a2b675c75fae503baa.md)

[2. XGBoost](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/2%20XGBoost%2064aad5a9039145c0bdb02ab7eeb1f788.md)

[3. Seq2Seq](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/3%20Seq2Seq%2031c21781d06d416d8bbe6c25e59b1e7f.md)

[4. DeepAR](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/4%20DeepAR%201564bd7f919b4741887a0d20f587c626.md)

[5. BlazingText](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/5%20BlazingText%205f27766e3a8049128549db7196ea2f76.md)

[6. Object2Vec](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/6%20Object2Vec%20d8081218ad9743b88c2537ae3e4873b2.md)

[7. Object Detection](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/7%20Object%20Detection%20d5ad4fc073814eb8bf9f6dfd05785026.md)

[8. Image Classification](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/8%20Image%20Classification%20483c9a86e48a42a39a5a497b459c2629.md)

[9. Semantic Segmentation](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/9%20Semantic%20Segmentation%2084e5f2b674fc458db883b8c41df412ea.md)

[10. Random Cut Forest](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/10%20Random%20Cut%20Forest%20f7204153a8b24a659f47a7f6bd171d4c.md)

[11. Neural Topic Model](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/11%20Neural%20Topic%20Model%208b40a1d1d3344a1682b36bc82d77e402.md)

[12. LDA](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/12%20LDA%202430c44ad1434fb4b43d46e02597d59c.md)

[13. KNN](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/13%20KNN%20cc7f7e6f0a0647c082fa8edd5d133528.md)

[14. K-Means](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/14%20K-Means%20a51a9145a0304c3d93bcab5b25813a40.md)

[15. PCA](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/15%20PCA%20eb87a47baf9847738daed7cd509d7ce0.md)

[16. Factorization Machines](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/16%20Factorization%20Machines%20d16aa3fabe57443eafaa95aa4c1cff1c.md)

[17. IP Insights](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/17%20IP%20Insights%20c68fb68740c14683898ef6c477d333e8.md)

[18. Reinforcement Learning](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/18%20Reinforcement%20Learning%20813defb2c316460689e92ff81c14ac42.md)

[19. Automatic Model Tuning](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/19%20Automatic%20Model%20Tuning%206c8cad96c2bb4eaea22f6a57fda6e40f.md)

[20. SageMaker and Spark](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/20%20SageMaker%20and%20Spark%206c2f448b83c34ec88fcaf37d1aa064e0.md)

[21. New SageMaker Features](12%20Amazon%20SageMaker%2034464f6e1b6c4ca69ceb01940be16782/21%20New%20SageMaker%20Features%20e46324ca93b648a688cfa5c4304f6d78.md)