# 11. Neural Topic Model

## Neural Topic Model: What’s it for?

- Organize documents into topics
- Classify or summarize documents based on topics
- It’s not just TF/IDF
    - “bike”, “car”, “train”, “mileage”, and“speed” might classify a document as“transportation” for example(although it wouldn’t know to call it that)
- Unsupervised
    - Algorithm is “Neural Variational Inference

---

## Neural Topic Model: What training input does it expect?

- Four data channels
    - “train” is required
    - “validation”, “test”, and “auxiliary” optional
- recordIO-protobuf or CSV
- Words must be tokenized into integers
    - Every document must contain a count forevery word in the vocabulary in CSV
    - The “auxiliary” channel is for the vocabulary
- File or pipe mode

---

## Neural Topic Model: How is it used?

- You define how many topics you want
- These topics are a latent representation based on top ranking words
- One of two topic modeling algorithms in SageMaker – you can try them both!

---

## Neural Topic Model: Important Hyperparameters

- Lowering mini_batch_size and learning_rate can reduce validation loss
    - At expense of training time
- Num_topics

---

## Neural Topic Model: Instance Types

- GPU or CPU
    - GPU recommended for training
    - CPU OK for inference
    - CPU is cheaper