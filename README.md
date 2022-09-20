# 2022 Samsung AI Challenge (3D Metrology) 1st place Solution

## Solution Overview
overview image

## Team member
정재윤, 위성진, 장준보

## Code Running Environment
> ## run at local
> **use docker image of paperspace gradient Scratch docker**
> https://hub.docker.com/r/paperspace/gradient-base \
> \
> **docker tag** \
> pt112-tf29-jax0314-py39-20220803
> ## Machine Environment
> Intel i0-10900 cpu, RTX3090 gpu

## File Structure
```
┖ [ST]cycle_wider_BNGN.ipynb - Train gan model for transfer simulation sem image to train sem image style.
┖ [CNN]Train.ipynb - Train efficientnet_b0 for Case Classifier
┖ [INF]Inference.ipynb - simularity model for get depth image
┖ [open.zip - data download from [2022 Samsung AI Challenge (3D Metrology)](https://dacon.io/competitions/official/235954/data)
```

## Dataset
We train and evaluate our model using the dataset from [2022 Samsung AI Challenge (3D Metrology)](https://dacon.io/competitions/official/235954/data)

we assume that you have downloaded it and placed based on File Sturcture.

## Submission Process
### Train Process
1. Run All code in [ST]cycle_wider_BNGN.ipynb for train domain transfer GAN and make domain transferred image that transferred from simulation sem to train sem. the transferred image will be saved in `./processed_data` folder. *caution* you need to log in wandb to track model progress

2. Run All code in [CNN]Train.ipynb for train case classification model. classification model's pth file will be saved as `./cnn_classifier.pth`.

### Test Process
1. Run All code in [INF]Inference.ipynb for generate depth data from test sem image. test sem image and ziped file will be saved in `./Submission_F` folder.