# Kaggle-Lyft-Motion-Prediction-for-Autonomous-Vehicles
Kaggle-Featured Code Competition





## Task
In this competition, you’ll apply your data science skills to build motion prediction models for self-driving vehicles. 

You'll have access to the largest Prediction Dataset ever released to train and test your models. 

Your knowledge of machine learning will then be required to predict how cars, cyclists,and pedestrians move in the AV's environment.



### metrics page in the L5Kit repository
https://github.com/lyft/l5kit/blob/master/competition.md


### Dataset Formats
https://github.com/lyft/l5kit/blob/master/data_format.md


### numpy structured arrays
https://numpy.org/doc/stable/user/basics.rec.html

### pytorch
https://pytorch.org/


### SAVING AND LOADING MODELS
https://pytorch.org/tutorials/beginner/saving_loading_models.html

### ResNet in PyTorch - GitHub
https://github.com/pytorch/vision/blob/master/torchvision/models/resnet.py


## Data and EDA
### Files:
- aerial_map - an aerial map used when rasterisation is performed with mode "py_satellite"
- semantic_map - a high definition semantic map used when rasterisation is performed with mode "py_semantic"
- sample.zarr - a small sample set, designed for exploration
- train.zarr - the training set, in .zarr format
- validate.zarr - a validation set (roughly the size of train)
- test.csv - the test set, in .zarr format
- mask.npz - a boolean mask for the test set. All and only the agents included in the mask should be submitted
- *sample_submission.csv - two sample submissions, one in multi-mode format, the other in single-mode

## L5kit
### 1 Overview
https://github.com/lyft/l5kit/blob/master/README.md

### 2 Competition
https://github.com/lyft/l5kit/blob/master/competition.md

### 3 Coordinate Systems in L5Kit
https://github.com/lyft/l5kit/blob/master/coords_systems.md

### 4 Dataset Formats
https://github.com/lyft/l5kit/blob/master/data_format.md

### 5 How to contribute
https://github.com/lyft/l5kit/blob/master/how_to_contribute.md


## Raster

# Dependency of parameters/models on leaderboard score

## 1) raster size
       - raster size (384, 384)  :  LB 3593.289
       - raster size (300, 300)  :  LB 2354.393
       - raster size (224, 224)  :  LB 1584.348
## 2) Batch size for training
       - batch size   12 :  LB 1584.348   #raster size (224, 224), num_steps 10,000 
       - batch size   32 :
       - batch size   64 :   evaluating
## 3) num_steps for training 
       - num_steps   10,000 : LB 1584.348  #raster size (224, 224), batch size 12
       - num_steps   15,000 :
       - num_steps   20,000 :
## 4) Models
       - resnet 50, resnet 18, etc.

------

# Code Requirements
## This is a Code Competition
Submissions to this competition must be made through Notebooks. 

### Please note that for this competition training is not required in Notebooks.

In order for the "Submit to Competition" button to be active after a commit, the following conditions must be met:

- CPU Notebook <= 9 hours run-time
- GPU Notebook <= 9 hours run-time
- TPU Notebook <= 3 hours run-time

Freely & publicly available external data is allowed, including pre-trained models.

Submission file must be named submission.csv

------

# Lyft Conpetition Plan/strategy for higher LB Score

## Pytorch Baseline

### 1 Settup Dependencies
### 2 Load Datasets
### 3 Define a Model (CNN)
- Model
- Parameters
### 4 Train the Model --- Takes much time (>9 hours)
-> Separate from Teast/Prediction, 

-> W/O kaggle notebook. 
- Save the model
### 5 Prediction
-> W/ kaggle notebook
- load the model
- Test the model
### 6 Submit

## Ensamble Update
### Dependency of weights on LB Score
- weights = [0.3, 0.7]    LB:46.603
- weights = [0.35, 0.65]  LB:46.370
- weights = [0.4, 0.6]    LB:46.189   ---Original Score
- weights = [0.45, 0.55]  LB:46.082   ---Got Best Score
- weights = [0.5, 0.5]    LB:46.331




