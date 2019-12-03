## Learning Algorithm:

In order to build an agent that is able to solve the problem, I used a Deep-Q-Network with Fixed Deep-Q-Target approach to avoid any harmful form of correlation. Alson Experience replay technique was used to make the agent learns better by passing over the same experience multiple times. 

### Components:

1. Deep-Q-Network: consists of three fully connected layers along with relu function
2. Fixed Deep-Q-Target: consists of three fully connected layers along with relu function
3. Experience Replay: with a buffer to store the experience and sampling from it
4. Adam Optimizer: that optimizes the actions of the agent.

### Hyperparameters:

I have tried different values of some parameters until solving the environment in 212 episodes using the follwing parameters values:

* eps_start = 1.0      > starting value of epsilon, for epsilon-greedy action selection 
* eps_end = 0.01       > minimum value of epsilon
* eps_decay = 0.98     > multiplicative factor (per episode) for decreasing epsilon
* BUFFER_SIZE = 1e5    > replay buffer size
* BATCH_SIZE = 64      > minibatch size
* GAMMA = 0.99         > discount factor
* TAU = 1e-3           > for soft update of target parameters
* LR = 5e-4            > learning rate 
* UPDATE_EVERY = 4     > how often to update the network 


## Plot of Rewards:

![plot of rewards](/download.png)

## Ideas for Future Work:

There are many ideas that can improve the agent's performance dramatically like the following:

1. Trying aither modified versions of DQN like double DQN or Dueling DQN.
2. updating the networks by adding convolutional layers.
3. Using Prioritized Experience Replay may improve the agent

