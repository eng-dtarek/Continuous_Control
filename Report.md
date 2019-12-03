## Learning Algorithm:

In order to build an agent that is able to solve the problem, I used Deep Deterministic Policy Gradient approach which is a model-free, off-policy actor-critic algorithm using deep function approximators that can learn policies in high-dimensional, continuous action spaces."They highlight that DDPG can be viewed as an extension of Deep Q-learning to continuous tasks". Experience replay is used to allow the RL agent to learn from past experience. In this problem the actions are no longer a discrete set of simple directions. The actions driving the movement of the arm are forces with different magnitudes and directions. If we base our exploration mechanism on random uniform sampling, the direction actions would have a mean of zero, in turn cancelling each other out. This can cause the system to oscillate without making much progress. So the Ornstein-Uhlenbeck process is used to add a certain amount of noise to the action values at each timestep. This noise is correlated to previous noise, and therefore tends to stay in the same direction for longer durations without canceling itself out. This allows the arm to maintain velocity and explore the action space with more continuity. I also used Batch normalization that improved the speed, performance, and stability of artificial neural networks by scaling the features to be within the same range throughout the model.


### Components:

* Actor Network: consists of three fully connected layers, batch normalizaton layer along with relu function and tanh function.

* Critic Network: consists of three fully connected layers, batch normalizaton layer along with relu function.

* Adam Optimizer: that optimizes the actions of the agent.

* Experience Replay: with a buffer to store the experience and sampling from it.

* Ornstein-Uhlenbeck: add a certain amount of noise to the action values at each timestep.

### Hyperparameters: 

I have tried different values of some parameters until solving the environment in 883 episodes using the follwing parameters values:

* BUFFER_SIZE = int(1e5) 
* BATCH_SIZE = 125      
* GAMMA = 0.99         
* TAU = 1e-2            
* LR_ACTOR = 1e-3      
* LR_CRITIC = 1e-4     
* WEIGHT_DECAY = 0      
* mu = 0.               
* sigma = 0.1          
* theta = 0.15            

## Plot of Rewards:

![plot of rewards](/download.png)

## Ideas for Future Work:

There are many ideas that can improve the agent's performance dramatically like the following:

* Trying different hyperparameters.
* Changing the neural networks architectures.
* Using prioritized experience Replay may improve the agent.
* Implementing the distributed training solution version of the unity environment.
