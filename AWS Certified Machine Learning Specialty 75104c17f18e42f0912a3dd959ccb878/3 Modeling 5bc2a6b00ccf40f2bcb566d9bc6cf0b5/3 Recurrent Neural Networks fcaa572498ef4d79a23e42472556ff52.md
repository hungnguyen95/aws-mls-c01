# 3. Recurrent Neural Networks

## RNN’s: what are they for?

- Time-series data
    - When you want to predict future behavior based on past behavior
    - Web logs, sensor logs, stock trades
    - Where to drive your self-driving car based on past trajectories
- Data that consists of sequences of arbitrary length
    - Machine translation
    - Image captions
    - Machine-generated music

---

## A recurrent neuron

![3%20Recurrent%20Neural%20Networks%20fcaa572498ef4d79a23e42472556ff52/Untitled.png](3%20Recurrent%20Neural%20Networks%20fcaa572498ef4d79a23e42472556ff52/Untitled.png)

---

## Another way to look at it

![3%20Recurrent%20Neural%20Networks%20fcaa572498ef4d79a23e42472556ff52/Untitled%201.png](3%20Recurrent%20Neural%20Networks%20fcaa572498ef4d79a23e42472556ff52/Untitled%201.png)

---

## RNN topologies

- Sequence to sequence
    - i.e., predict stock prices based on series of historical data
- Sequence to vector
    - i.e., words in a sentence to sentiment
- Vector to sequence
    - i.e., create captions from an image
- Encoder -> Decoder
    - Sequence -> vector -> sequence
    - i.e., machine translation

---

## Training rnn’s

- State from earlier time steps get diluted over time
    - This can be a problem, for example when learning sentence structures
- LSTM Cell
    - Long Short-Term Memory Cell
    - Maintains separate short-term and long-term states
- GRU Cell
    - Gated Recurrent Unit
    - Simplified LSTM Cell that performs about as well

---

## Training rnn

- It’s really hard
    - Very sensitive to topologies,choice of hyperparameters
    - Very resource intensive
    - A wrong choice can lead to a RNN that doesn’t converge at all.