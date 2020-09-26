# Kaggle-Lyft-Motion-Prediction-for-Autonomous-Vehicles
Kaggle-Featured Code Competition




# Task
### In this competition, you’ll apply your data science skills to build motion prediction models for self-driving vehicles. 

### You'll have access to the largest Prediction Dataset ever released to train and test your models. 

### Your knowledge of machine learning will then be required to predict how cars, cyclists,and pedestrians move in the AV's environment.

# References

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



# Data

### The dataset is structured as follows:       
        scenes,   aerial_map,   semantic_map
   ### Under scenes, we have:
        sample.zarr,   test.zarr,   train.zarr,   validate.zarr,   mask.npz *   
   ### Each .zarr file contains a set of:
        scenes,   frames,   agents,   traffic_light_faces,   agents_mask**  
 
  *:   In test, the mask (provided in files as mask.npz) masks out any test object for which predictions are NOT required.
  
**:   A mask that (for train and validation) masks out objects that aren't useful for training.       




### Files:
- aerial_map - an aerial map used when rasterisation is performed with mode "py_satellite"
- semantic_map - a high definition semantic map used when rasterisation is performed with mode "py_semantic"
- sample.zarr - a small sample set, designed for exploration
- train.zarr - the training set, in .zarr format
- validate.zarr - a validation set (roughly the size of train)
- test.csv - the test set, in .zarr format
- mask.npz - a boolean mask for the test set. All and only the agents included in the mask should be submitted
- *sample_submission.csv - two sample submissions, one in multi-mode format, the other in single-mode


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

# Kaggle Lyft Competition Update
## Lyft Competition Plan/strategy for higher LB Score
- 1. Pytorch Update 
- 2. Ensamble Update

------

# 1. Pytorch Update





## Pytorch process

### 1 Settup Dependencies
### 2 Load Datasets
### 3 Define a Model (CNN)
- Model
- Parameters
### 4 Train the Model


- Save the model
### 5 Prediction

- load the model
- Test the model
### 6 Submit


## Dependency of parameters/models on leaderboard score

## 1) raster size
       - raster size (384, 384)  :  LB 3593.289
       - raster size (300, 300)  :  LB 2354.393
       - raster size (224, 224)  :  LB 1584.348
## 2) Batch size for training
       - batch size   12 :  LB 1584.348           #raster size (224, 224), num_steps 10,000 
       - batch size   32 :
       - batch size   64 :   evaluating
## 3) num_steps for training 
       - num_steps   10,000 : LB 1584.348         #raster size (224, 224), batch size 12
       - num_steps   15,000 :
       - num_steps   20,000 :
## 4) learning rate 
       - lr   1e-2 : 
       - lr   1e-3 : LB 1584.348
       - lr   1e-4 :
## 5) Optimizer 
       - optimizer   Adam : LB 1584.348
       - optimizer   SGD  :
       - optimizer   ASGD :
## 6) Models
       - Resnet 50  :  LB 1584.348
       - Resnet 18  :  
       - EfficientNet  :


## Issue --- Takes much time to compute (>9 hours)
-> W/ kaggle notebook is required in Testing/Prediction

### ideas:
-> Separate Training from Testing/Prediction

-> W/O kaggle notebook in Training

------

# 2. Ensamble Update
### Dependency of weights on LB Score
### 1 and 2
- weights = [0.3, 0.7]    LB:46.603
- weights = [0.35, 0.65]  LB:46.370
- weights = [0.4, 0.6]    LB:46.189   ---Original Score
- weights = [0.420, 0.580]  LB:46.084
- weights = [0.425, 0.575]  LB:46.069
- weights = [0.430, 0.570]  LB:46.061  
- weights = [0.435, 0.565]  LB:46.059   ---Got Best Score
- weights = [0.440, 0.560]  LB:46.062
- weights = [0.45, 0.55]  LB:46.082   
- weights = [0.475, 0.525]  LB:46.179  
- weights = [0.5, 0.5]    LB:46.331
### 1 and 3
- weights = [0.5, 0.5]    LB:46.641
- weights = [0.4, 0.6]    LB:45.064
- weights = [0.3, 0.7]    LB:44.346
- weights = [0.15, 0.85]    LB:42.173
- weights = [0.105, 0.895]   LB:41.855
- weights = [0.1, 0.9]    LB:41.840
- weights = [0.095, 0.905]   LB:41.830
- weights = [0.090, 0.910]   LB:41.825  ---Got Best Score
- weights = [0.085, 0.915]   LB:41.825
- weights = [0.080, 0.920]   LB:41.829
- weights = [0.05, 0.985]    LB:41.947

### 2 and 3
- weights = [0.5, 0.5]    LB:132.087

### 1 and 4
- weights = [0.105, 0.895]   LB:34.058
- weights = [0.1, 0.9]    LB:33.756
- weights = [0.095, 0.905]   LB:33.745 
- weights = [0.085, 0.915]  LB:33.726
- weights = [0.075, 0.925]  LB:33.718  ---Got Best Score
- weights = [0.070, 0.930]  LB:33.719
- weights = [0.065, 0.935]  LB:33.723
- weights = [0.05, 0.95]  LB:33.748
