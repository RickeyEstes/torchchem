# MolDQN-pytorch

PyTorch implementation of RetinaNet object detection as described in [Optimization of Molecules via Deep Reinforcement Learning](https://www.nature.com/articles/s41598-019-47148-x)
by Zhenpeng Zhou, Steven Kearnes, Li Li, Richard N. Zare and Patrick Riley.

## Installation

## <a name="source"></a>From source:

1) Install `rdkit`.  
   `conda create -c rdkit -n my-rdkit-env rdkit`  
   `conda activate my-rdkit-env`  
   `conda install -c conda-forge rdkit`  
   
2) Clone this repository.  
   `https://github.com/deepchem/torchchem.git`  
   `cd MolDQN-pytorch`
   
3) Install the requirements given in `requirements.txt`.  
   `pip install -r requirements.txt`  
   
4) Install `baselines`.  
   `pip install "git+https://github.com/openai/baselines.git@master#egg=baselines-0.1.6"`  
   
## From Docker:

Using a docker image requires an NVIDIA GPU.  If you do not have a GPU please follow the directions for [installing from source](#source)
In order to get GPU support you will have to use the [nvidia-docker](https://github.com/NVIDIA/nvidia-docker) plugin.
``` bash
# Build the Dockerfile in Dockerfiles/Dockerfile to create a Docker image.
docker build -t MolDQN_pytorch:latest Dockerfile .

# This will create a container from the image we just created.
nvidia-docker run -[Options] MolDQN_pytorch:latest python path/to/main.py
```

## Training the MolDQN:

`python main.py`

## Results:

The following was the reward curve obtained when the model was trained for 5000 episodes on a single property optimization task (QED in this case).

<img src="https://github.com/aksub99/MolDQN-pytorch/blob/master/Results/plots/episode_reward.svg" height="500" width="500">

