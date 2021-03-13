## Report
---
The aim of the project was to train a Deep Reinforcement Agent to solve the *_Udacity's Banana Collecter Unity Env_* [(Windows x64 verion)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip). 

For details on the nature of the environment see README.md

## Algorithm

The agent was trained used a `Deep Q-Network` along with a `Replay Buffer` implementation. This was sufficient to solve the environment in 1072 episodes. 

### Hyper Parameters  

```
n_episodes = 3500       # max number of iterations`
eps_start = 1           # initial epsilon value
eps_end = 0.1           # minimum epsilon value
eps_decay = 0.995       # epsilon decay rate 

BUFFER_SIZE = int(1e6)  # replay buffer size
BATCH_SIZE = 256        # minibatch size
GAMMA = 0.99            # discount factor
TAU = 5e-3              # for soft update of target parameters
LR = 1e-3               # learning rate
UPDATE_EVERY = 4        # how often to update the network
```

## Learning Algorithm 
The `Agent` is trained using the DQN training helper function in the `Naviation.ipynb`. The training happens in an episodic manner until the environment is natually solved or maximum number of epsiodes are completed. The environment is considered solved when the average reward over 100 episodes is at least +13.
Each episode considers until the enviornment naturally completes.A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.

- The `DQN` selects an action using an epsilon-greedy policy after receiving the state input from the environment. 
- At the beginning, the value of epsilon is 1 or close to 1, so the initial actions take by the agent are randomly selected. 
- The `DQN` agent observes the new state and identifies the reward recieved from the action taken. 
- The agent then adds the `(state, action, reward, next_state, done)` to the ReplayBuffer which is a memory buffer to store the experiences. 
- After `UPDATE_EVERY` time steps, a `BATCH_SIZE ` set of experiences  are sampled from the ReplayBuffer. 
- The agent then uses this sample of experiences to learn from. 
- The target is idetified by using the `qnetwork_target`, `MSE` loss is used to measure the error between the output of the `qnetwork_target` and the `qnetwork_local`
- The `qnetwork_target` is then soft updated using `θ_target = τ*θ_local + (1 - τ)*θ_target` formula.  

### Neural Network
The [QNetwork model](https://github.com/diarmaidfinnerty/DRF_Navigation/blob/main/model.py) consisted of a simple feedforward neural network containing a single hidden layer. 

The neural network had:
    - 37 input nodes, relating to each of the state space dimensions.
    - 64 hidden layer nodes.
    - 4 output nodes, relating to each of 4 actions the agent can take. 
    - ReLU activation functions. 

## Training Rewards

#### Rewards plot
![Plot of Rewards](TrainingRewardsPlot.png)
#### Reward progression during training. 
![Training Rewards By Episode](TrainingRewards.png)

## Future Work
The agent could be improved by utilising a different learning algorithm. 

Examples of possible algorithms are:

    - Dueling DQN Network
    - Double DQN Network
    
As well as using an improved memory method such as:

    - Prioritized Memory

