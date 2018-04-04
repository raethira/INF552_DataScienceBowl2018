# Investigating Focal and Dice Loss for the Kaggle 2018 Data Science Bowl 
#### Author : Adrien Lucas Ecoffet
#### [ref](https://becominghuman.ai/investigating-focal-and-dice-loss-for-the-kaggle-2018-data-science-bowl-65fb9af4f36c)

- experiments and implementations with three important loss functions for the Kaggle 2018 data science bowl and compares their effects on a simplified implementation of U-Net
- **Problem Statement** of 2018 Data Science Bowl
    - consists of finding which pixel in images such as the one below are part of a cell nucleus and if so which nucleus (in this case, basically all the white/gray spots are nuclei)
    ![image.png](https://cdn-images-1.medium.com/max/1600/1*VoC5XsQMaQODli00cuXtkQ.png)
- This can thus be seen as an instance segmentation problem, although comptetitors have been using semantic segmentation algorithms such as U-Net which we will do here as well for simplicity

- The loss functions which we will investigate are binary cross entropy(referred to as "nll" in the notebook because my intitial version used the related NLLLoss instead of BCE), the soft-dice loss(introduced in "V-Net: Full convolutionaly Neural networks for volumentric Medical Image Segmnentation") and generally considered to be useful for segmentation problems and focal loss the investigation of which is the main focus of this notebook.
- focal loss is described in "Focal Loss for Dense Object Detection" and is simply a modified version of binary cross entropy in which the loss for confidently correctly classified labels is scaled down so that the network focusses more on incorrect and low confidence labels than on increasing its confidence in the already correct labels