[image1]: https://github.com/MarkusSchmitz/DRLND_Continuoues_Control/blob/master/reacher.gif?raw=true "Trained Agent"


# Project 2: Continuous Control

### Introduction

For this project, the work will be with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment.

![Trained Agent][image1]

This environment contains two agents which are instantiated as tennis rackets. The goal is to make these agents play harmoniously in order to achive a maximum amounts of ball exchanges. Each time a ball is hit by an agent, the acting agent's score is increased by 0.1. If the ball is lost (hitting the net, leaving the field boundaries or hitting the ground) the serving agent's is decreased by 0.1. As scoring involves actions from both agents, the returned reward is the maximum score awarded to either agent. In order to achieve high scores, the agents must interact with each other and optimize on both being able to make the exchange.

The state of the environment contains the position and velocity of the agents as well as the tennis ball. Each action is a vector with two continoues numbers, corresponding to force applied to movement (from and towards net) as well as jumping. Every entry in the action vector is a value between -1 and 1.

In order to solve the environment, the agent must reach a average score of 0.5 over 100 consecutive episodes.


### Motivation
There are many real world examples for environments, where two autonomous agents must cooperate in order to achieve a maximum return. This problem has been discussed thoroughly in the essence of game theory. In production environments, many gears, literally and not, must interlock in order to achive peak performance. Be it the different elements of the supply chain or robots working on a single item simultaneously. Making agents increase their combined reward might be the most relevant scenario in the world of manufacturing.


### Solving the Environment

The environment contains two tessis racket agents.
In order to solve the environment, the agents must reach an average score of 0.5 over 100 consecutive episodes by playing together.
```python
env = UnityEnvironment(file_name='Reacher.app')
```
### Getting Started
This sample of the project was computed on a MacOS with no GPU Accelearation.
In order to replicate the environent, follow these steps:


Download the environment from one of the links below. You need only select the environment that matches your operating system:

Linux: click here
Mac OSX: click here
Windows (32-bit): click here
Windows (64-bit): click here
Place the extracted folder in the BananaFeast GitHub repository, in the base directory.

Install the dependancies as stated in the [DRLND repository](https://github.com/udacity/deep-reinforcement-learning#dependencies).

in the console activate your environment created in step 2 and install the seaborn package with:


1. Create a new environment with Python 3.6 with Anaconda.
	```bash
	conda create --name drlnd python=3.6 
	activate drlnd
	```
2. Install the dependancies as stated in the [DRLND repository](https://github.com/udacity/deep-reinforcement-learning#dependencies)

3. Install the necessary dependencies in the environment with pip and conda:
	- __Install Unity ML-Agents__
	```bash
	pip install --user mlagents, unityagents
	```	
	```bash	
	- __Install Pytorch__
	conda install pytorch torchvision -c pytorch
	
	or

	conda install pytorch torchvision cudatoolkit=10.0 -c pytorch

	```
	- __Install tqdm__
	```bash
	pip install tqdm
	```
4. Download the `Reacher` environment from one of the links below and select the environment that matches your Windows operating system:

Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)

Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)

Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)

Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)


### Train the agent 
Use the `tennis.ipynb` in order to train the agent. The weights of the target nets are also saved as checkpoints.
At the beginning of the notebook you can set the "train" variable to true or false.
Setting the variable to True will allow you to train the agent with your parameters.
Setting the variable to False will let you observe a trained agent.