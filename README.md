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




