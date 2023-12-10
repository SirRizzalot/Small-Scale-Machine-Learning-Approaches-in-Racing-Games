# Project Introduction

This repository houses the code used by Group #2 in our racing game reinforcement learning project.

If you'd like to view sample graphs and sample videos of our various agents, the samples.ipynb notebook can be run through Google Colab.
This notebook will produce mean rewards, standard deviations, and recordings for a control agent, an agent which has only been pre-trained, and a balanced agent which has undergone both pre-training and standard training.

## Source File Information

The "src" folder contains all the code and gathered datasets involved with the project:

1. "car_racing.py": This file contains the modified environment which we used to collect training data by playing through the car racing environment ourselves on a Linux OS system. We are providing this file as a reference, but it should not be run in any capacity because sample training data has already been provided.
2. "states_data.npy": This file contains the "input" of the training data. It consists of 140 elements matching observation space of the car racing environment after grayscaling and framestacking.
3. "actions_data.npy": This file contains the "output" of the training data. It consists of 140 elements matching the continuous action space of the car racing environment.
4. "pre_training.ipynb": This file contains the code necessary to conduct the pre-training process and produce weights for an SB3 PPO agent. 
5. "standard_training.ipynb": This file contains the code necessary to conduct the standard training process and produce weights for an SB3 PPO agent.
6. "evaluation.ipynb": This file contains the evaluation framework for producing mean reward and standard deviation metrics, as well as video recordings, given agent weight files.

## Sample Video Recordings

All recordings used in our final presentation, as well as a new recording demonstrating the performance of the continuous control agent, are included in the "videos" folder.

![example](https://github.com/SirRizzalot/Small-Scale-Machine-Learning-Approaches-in-Racing-Games/blob/main/videos/replay_control.mp4)

# Execution Instructions
The following sections detail instructions for running several notable project processes. Before attempting any of the processes, please import "pre_training.ipynb", "standard_training.ipynb", and
"evaluation.ipynb" into Google Colab.

## Creating a Control Agent

To train a standard, control agent on the car racing environment, simply run all cells in "standard_training.ipynb" from start to finish.
This will produce an agent trained on the equivalent of 100,000 timesteps, though the cell labelled "Load Agent & Perform Additional Training" can be run repeatedly for further training.
If you wish to evaluate or record an agent, the resulting weights must be downloaded and uploaded into an "evaluation.ipynb" runtime.

## Creating a Pre-Trained Agent

To train an exclusively pre-trained agent on the car racing environment, start a "pre_training.ipynb" runtime in Google Colab.
From there, "states_data.npy" and "actions_data.npy" should be uploaded to the runtime. Then, run all the cells from start to finish.
This will produce an agent pre-trained on the equivalent of 100,000 timesteps, though the cell labelled "Load Agent & Perform Additional Training" can be run repeatedly for further training.
If you wish to evaluate or record an agent, the resulting weights must be downloaded and uploaded into an "evaluation.ipynb" runtime.

## Creating a Balanced Agent

To train a balanced agent on the car racing environment, start a "pre_training.ipynb" runtime in Google Colab.
From there, "states_data.npy" and "actions_data.npy" should be uploaded to the runtime. Then, run all the cells from start to finish and download the resulting weights.
Proceed by uploading the weights to a "standard_training.ipynb" runtime in Google Colab. Run all the cells prior to the two training cells, then execute the "Load Agent & Perform Additional Training" cell twice.
This will produce an agent pre-trained on the equivalent of 100,000 timesteps and trained normally on the equivalent of an additional 100,000 timesteps, though the cell labelled "Load Agent & Perform Additional Training" can be run repeatedly for further training.
If you wish to evaluate or record an agent, the resulting weights must be downloaded and uploaded into an "evaluation.ipynb" runtime.

## Evaluating an Agent

To evaluate a particular agent on both seeded and unseeded environments, upload a set of weights produced by any of the previously described processes into an "evaluation.ipynb" runtime.
Then, run all the cells from start to finish.
