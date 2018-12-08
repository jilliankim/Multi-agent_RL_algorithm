### Learning Algorithm:
In this project I trained two agents to play table tennis. For this environment I used Multi-Agent Deep Deterministic Policy Gradient (MADDPG) algorithm and the neural network for both Actor and Critic has two hidden layers with 256 nodes each.
Here I trained each agent seperately using the same Replay Buffer so that each agent learns from other agent's experiences. When an epsilon decay of 0.99 was used the environment solved in 896 episodes but with a learning rate decay of 0.9, the environment solves in 304 episodes.

Also changed training and updating of the target network only after adding the last agent's environment variables to memory. This way we don't run into the risk of updating the target network frequently.

### Hyper parameters used:

BUFFER_SIZE = int(1e5)  # replay buffer size

BATCH_SIZE = 128        # minibatch size

GAMMA = 0.99            # discount factor

TAU = 1e-2              # for soft update of target parameters

LR_ACTOR = 1e-4         # learning rate of the actor 

LR_CRITIC = 1e-3        # learning rate of the critic

WEIGHT_DECAY = 0        # L2 weight decay

### Results:
Below are the results and a plot of rewards per episode is included to illustrate that the agents get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents).


### Future Ideas:
Here I trained each agent seperately where each one observed it's own environment and state. Whereas I would like to train the agents by passing both states to the agents.
Further I would like to apply the same algorithm to train agents to play soccer. Since both agents were able to learn it's own reward function, this should be possible.
