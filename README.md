# 2022 Samsung AI Challenge (3D Metrology) 1st place Solution
AI solution that produces depth image from SEM image

## [Solution presentation](./Samsung-sem-1st.pdf)
you can see our presentation at [Samsung-sem-1st.pdf](./Samsung-sem-1st.pdf)

## Solution Overview
![overview image](./figures/overview.png)

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
> Intel i9-10900 CPU, RTX3090 GPU, window 10 anaconda3 jupyter notebook

## File Structure
```
┖ figures
  ┖ ~
┖ [ST]cycle_wider_BNGN.ipynb
┖ [CNN]Train.ipynb
┖ [INF]Inference.ipynb
┖ open.zip
┖ Readme.md
┖ Samsung-sem-1st.pdf
```

cycle folder
- model pth file and training image folder. It will be generated after [ST] or download weight.

[ST]cycle_wider_BNGN.ipynb 
- Train GAN model for transfer simulation sem image to train sem image style.

[CNN]Train.ipynb 
- Train efficientnet_b0 for Case Classifier

[INF]Inference.ipynb 
- similarity model for getting depth image

open.zip 
- data download from [2022 Samsung AI Challenge (3D Metrology)](https://dacon.io/competitions/official/235954/data)

Samsung-sem-1st.pdf
- code presentation written by korean

## Dataset
We train and evaluate our model using the dataset from [2022 Samsung AI Challenge (3D Metrology)](https://dacon.io/competitions/official/235954/data)

we assume that you have downloaded it and placed based on File Structure.

## Submission Process
### Train Process
1. Run All code in `[ST]cycle_wider_BNGN.ipynb` for train domain transfer GAN and make domain transferred image that transferred from simulation sem to train sem. the transferred image will be saved in the `./processed_data` folder. **you need to log in wandb for tracking model progress**

2. Run All code in `[CNN]Train.ipynb` for train case classification model. The classification model's pth file will be saved as `./cnn_classifier.pth`.
***
### Test Process
1. Run All code in `[INF]Inference.ipynb` to generate depth data from the test sem image. Test sem image and a zipped file will be saved in the `./Submission_F` folder.
