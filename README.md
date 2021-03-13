# DRF_Navigation
Using DQN to Train an agent to navigate in a large, square world - collect yellow bananas and avoid the blue bananas.


## Project Details
A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Therefore, the agent should collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. 

Four discrete actions are available, corresponding to:
- `0` - forward.
- `1` - backward.
- `2` - left.
- `3` - right.

The task is episodic, and in order to solve the environment, the agent must get an average score of +13 over 100 consecutive episodes.

## Installation
In order to run these scripts you will require
1. Follow instructions from this [link](https://github.com/udacity/deep-reinforcement-learning#dependencies) to ensure all dependencies are installed. 
2. Ensure that you execute *_cell 1_* of the `Naviagation.ipynb` notebook. `pip -q install ./python`.


## Setup
# Download the Unity Environment
For this project, you will not need to install Unity - this is because we have already built the environment for you, and you can download it from one of the links below. You need only select the environment that matches your operating system:

- [Linux: click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
- [Mac OSX: click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
- [Windows (32-bit): click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
- [Windows (64-bit): click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)

Then, place the file in the `p1_navigation/` folder in the DRLND GitHub repository, and unzip (or decompress) the file.
**Note:** This environment is similar but not identical to the The project environment is similar to, but not identical to the Banana Collector environment on the [Unity ML-Agents GitHub page](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#banana-collector). 

## Running the Code
1. Git clone the repository
2. Ensure that all steps in the Setup section have been completed
3. Run the `Navigation.ipynb` notebook. 
4. Alternatively, you can load the `checkpoint.pth` model weights. See the testing section of `Navigation.ipynb` for details.  
