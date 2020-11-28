# 18. Reinforcement Learning

## Reinforcement Learning

- You have some sort of agent that “explores” some space
- As it goes, it learns the value of different state changes in different conditions
- Those values inform subsequent behavior of the agent
- Examples: Pac-Man, Cat & Mouse game (game AI)
    - Supply chain management
    - HVAC systems
    - Industrial robotics
    - Dialog systems
    - Autonomous vehicles
- Yields fast on-line performance once the space has been explored

![18%20Reinforcement%20Learning%20813defb2c316460689e92ff81c14ac42/Untitled.png](18%20Reinforcement%20Learning%20813defb2c316460689e92ff81c14ac42/Untitled.png)

---

## Q-Learning

- A specific implementation of reinforcement learning
- You have:
    - A set of environmental states `s`
    - A set of possible actions in those states `a`
    - A value of each state/action `Q`
- Start off with Q values of 0
- Explore the space
- As bad things happen after a given state/action, reduce its Q
- As rewards happen after a given state/action, increase its Q

---

## Q-Learning

- What are some state/actions here?
    - Pac-man has a wall to the West
    - Pac-man dies if he moves one step South
    - Pac-man just continues to live if going North or East
- You can “look ahead” more than one step by using a discount factor when computing Q (here s is previous state, s’ is current state)

    `Q(s,a) += discount * (reward(s,a) + max(Q(s’)) – Q(s,a))`

---

## The exploration problem

- How do we efficiently explore all of the possible states?
    - Simple approach: always choose the action for a given state with the highest Q. If there’s a tie, choose at random
        - But that’s really inefficient, and you might miss a lot of paths that way
    - Better way: introduce an epsilon term
        - If a random number is less than epsilon, don’t follow the highest Q, but choose at random
        - That way, exploration never totally stops
        - Choosing epsilon can be tricky

---

## Fancy Words

- Markov Decision Process
    - From Wikipedia: **Markov decision processes (MDPs**) provide amathematical framework for modeling decision making in situationswhere outcomes are partly random and partly under the control of a decision maker.
    - Sound familiar? MDP’s are just a way to describe what we just did using mathematical notation.
    - States are still described as `s` and `s'`
    - State transition functions are described as: $P_a(s, s')$
    - Our “Q” values are described as a reward function: $R_a(s, s')$
- Even fancier words! An MDP is a **discrete time stochastic control process.**

---

## So to recap

- You can make an intelligent Pac-Man in a few steps:
    - Have it semi-randomly explore different choices of movement (actions) given different conditions (states)
    - Keep track of the reward or penalty associated with each choice for a given state/action (Q)
    - Use those stored Q values to inform its future choices
- Pretty simple concept. But hey, now you can say you understand reinforcement learning, Q learning, Markov Decision Processes, and Dynamic Programming!

---

## Reinforcement Learning in SageMaker

- Uses a deep learning framework with Tensorflow and MXNet
- Supports Intel Coach and Ray Rllib toolkits.
- Custom, open-source, or commercial environments supported.
    - MATLAB, Simulink
    - EnergyPlus, RoboSchool, PyBullet
    - Amazon Sumerian, AWS RoboMaker

---

## Distributed Training with SageMaker RL

- Can distribute training and/or environment rollout
- Multi-core and multi-instance

---

## Reinforcement Learning: Key Terms

- Environment
    - The layout of the board / maze / etc
- State
    - Where the player / pieces are
- Action
    - Move in a given direction, etc
- Reward
    - Value associated with the action from that state
- Observation
    - i.e., surroundings in a maze, state of chess board

---

## Reinforcement Learning: Hyperparameter Tuning

- Parameters of your choosing may be abstracted
- Hyperparameter tuning in SageMaker can then optimize them

---

## Reinforcement Learning: Instance Types

- No specific guidance given in developer guide
- But, it’s deep learning – so GPU’s are helpful
- And we know it supports multiple instances and cores