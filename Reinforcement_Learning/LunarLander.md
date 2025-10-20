# LUNAR LANDER
## Actions and states
![alt text](img/image-11.png)
where
![alt text](img/image-15.png)
## Reward function
![alt text](img/image-12.png)

## Goal
![alt text](img/image-14.png)

# APPROACH - (DEEP REINFORCEMENT LEARNING)
![alt text](img/image-16.png)
We want to create a training set and use a supervised learning method to train our neural network model. (x--->y)

We can do that using Bellman equation (for Q we can take as random number initially)
![alt text](img/image-17.png)

## Algorithm
![alt text](img/image-18.png)

## Refinement of architecture
The input now changes to state only and output 4 neurons of 4 different actions
![alt text](img/image-19.png)

## Epsilon- greedy policy
For choosing action, it is better to do 
* With probability 0.95, pick the action a that maximizes Q(s,a). "Greedy", "Exploitation"
* With probability 0.05, pick an action a randomly. "Exploration"
![alt text](img/image-20.png)

Start epsilon high and gradually decrease over time. (1.0 ---> 0.01)

## Mini-batch 
Instead of using:

* All data (batch gradient descent)

* Or just one example at a time (stochastic gradient descent)

Mini-batch gradient descent uses a small subset of the data—called a mini-batch—to compute the gradient and update the model parameters.
![alt text](img/image-21.png)

*So instead of using the 10000 most recent tuples to create the training set. We only need to use 1000 examples.

## Soft update
![alt text](img/image-22.png)