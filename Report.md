## Learning Algorithm an Training

We re-use the DQN from the previous class with the following where we use a network with 2 fully connected layers of size. The input layer is the size of the state and the output layer is of the size of the action space.

I experimented with different learning rates and gamma factors, the following parameters led to the best results:

BUFFER_SIZE = int(1e5)  # replay buffer size
BATCH_SIZE = 64         # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR = 5e-4               # learning rate 
UPDATE_EVERY = 4        # how often to update the network

## Training and Results

In p1_navigation/Navigation.ipynb, we have the exploration of the environment and the training of the DQN agent using 2000 episodes of maximum length 1000. We start with an epislon of 1 and decaying by 0.995.

In p1_navigation/Navigation_inference.ipynb, we have the execution of the agent over 500 episodes of maximum length of 1000. **Leading to an average reward of 19.0**


##  Future work

As next steps, we can focus on two aspects: the algorithms to use and the training, 

1. **Explore Rainbow** As the litterature showed, Raibow that combines different enhancing techniques (DDQN, Dueling DQN, Noisy DQN, etc.) shows the best results for DQNs. We will directly use this algorithms as it may not be worth it to try with DQN enhanced by only one approach (e.g. DDQN).
2. **Extensive finetuning of the hyperparameters** For this work, I only tried different values for the learning rates (LR) and gamma, due to GPU limitations. However, we can do extensive hyperparameter exploration (size of hidden layers in the network, other valuers of gamma and LR, different strategy for the epsilon exploration, etc.).
