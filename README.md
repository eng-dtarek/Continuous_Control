# Project 2: Continuous Control

## Introduction

For this project, we will work with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment and solve it using RL models for continuous actions/controls.

In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

## Distributed Training

For this project, can be done with two separate versions of the Unity environment:

* The first version contains a single agent.
* The second version contains 20 identical agents, each with its own copy of the environment (see here for more information).

In this repository I solved version 1 with a single agent.

## Solving the Environment

The task is episodic, and in order to solve the environment, the agent must get an average score of +30 over 100 consecutive episodes.


## Approach and solution

The notebook Continuous_Control.ipynb contains the code to set up the environment and the outer episode iteration to solve the reinforcement problem. My solution uses a Deep Deterministic Policy Gradient approach with experience replay, see this [paper](https://arxiv.org/pdf/1509.02971.pdf).

The agent, the deep Q-Network and memory buffer are implemented in the file ddpg_agent.py. The deep learning architectures for both actor and critic are defined in model.py.

## Dependencies

To set up your python environment to run the code in this repository, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

    * Linux or Mac:

    ```
    conda create --name continuous_control python=3.6
    source activate continuous_control
    ```

    * Windows:
    ```
    conda create --name continuous_control python=3.6 
    activate continuous_control
    ```
2. Clone the repository (if you haven't already!), and navigate to the python/ folder. Then, install several dependencies.

```
git@github.com:eng-dtarek/Continuous_Control.git
cd Continuous_Control/python
pip install .
```

3. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the continuous_control environment.

```
python -m ipykernel install --user --name continuous_control --display-name "continuous_control"
```

4. Before running code in a notebook, change the kernel to match the continuous_control environment by using the drop-down Kernel menu.


## Getting Started

1. Download the environment from one of the links below. You need only select the environment that matches your operating system:

* Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
* Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
* Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
* Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)
* For AWS: To train the agent on AWS (without [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) to obtain the "headless" version of the environment. The agent can not be watched without enabling a virtual screen, but can be trained. (To watch the agent, one can follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the Linux operating system above.)

2. Place the file in the repository, in the repository, and unzip (or decompress) the file.

3. Follow the instructions in Continuous_Control.ipynb to get started with training your own agent!
