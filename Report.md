## Learning algorithm
I used the DDPG learning algorithm based on the [Continous control with deep reinforcement learning](https://arxiv.org/pdf/1509.02971.pdf) paper (Lillicrap et al., 2016). The starting code was based on the Bipendulum implementation introduced during the class.

DDPG is an actor-critic method where the Critic learns from the value function and it determines how the Actor policy improves. To decrease the instability of the model, I used a replay buffer and a soft target update. 

## Model architecture
The actor model is a neural network with one hidden layer with size 256. I used ReLU as the activation function and tanh is used in the final layer to return the action output.

The critic model is a neural network with four hidden layers of size 256, 256, 128 and 64. I used ReLU as the activation function and tanh is used in the final layer to return the action output.

## Hyperparameters
I steak with the hyperparameters introduced in the Bipendulum implementation class.

BUFFER_SIZE = int(1e6)  
BATCH_SIZE = 128        
GAMMA = 0.99            
TAU = 1e-3              
LR_ACTOR = 1e-4          
LR_CRITIC = 3e-4        
WEIGHT_DECAY = 0.0001


## Training plots
I solved the environment in 210 episodes. I used Udacity's GPU and it took me around 20 minutes to solve the environment and something more than 30 minutes and 42 seconds to iterate over 300 episodes.

![First_training_1](/images/Capture1.PNG)

![Second_training_2](/images/Capture2.PNG)

![Third_training_3](/images/Capture3.PNG)

![Fourth_training_4](/images/Capture4.PNG)

A previous implementation of the DDPG agent gave me this result.

![First_training](/images/First_training.PNG)
## Ideas for future work
As introduced in the [Benchmarking Deep Reinforcement Learning for Continuous Control](https://arxiv.org/pdf/1604.06778.pdf) Truncated Natural Policy Gradient (TNPG) and Trust Region Policy Optimization (TRPO)  (Schulman et al., 2015) should improve the learning speed of the algorithm. In addition to that, I could use the simulator with 20 agents to speed up learning.
