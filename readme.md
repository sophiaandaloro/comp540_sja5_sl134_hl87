# Code Bundle for 2020 COMP 540 term project

### Sophia Andaloro, Shixiao Liang, Hongyi Liu
### comp540_sja5_sl134_hl87

This bundle includes 3 notebooks and 3 folders and 1 py file. The notebooks reflects how we trained models and make final submissions but our result cannot be produced by running these notebooks. We put our models and auxiliary file in the folders.

irv2_skeleton_model.ipynb shows how we handled the data and how we trained models. Top-scoring models and weights were saved and put in ./models. This notebook can be adjusted on the datagenerator cells to account for varying model inputs and augmentation/preprocessing procedures. That is how we constructed our various classifiers.
From here the hyperparameters can be optimized. We do not have a scanner or automatic stopping because by the point we built final models, we would stop training and restart with decreased learning rates once we saw "stalling" of the validation score. 
The parameters that we used for the final model are given in the paper, and all of the parameters for the secondary ensemble models fall within the bounds of safety also laid out in the same table. 


ensemble_prepare.ipynb loads these models and produce auxiliary predictions. We found the most convenient way to reset our GPU and load another model after finishing using one is to restart the kernel. As a result this notebook cannot be run through. Predictions were saved in ./predictions

ensemble.ipynb loads files in ./predictions and produce submission.csv. If files in ./predictions were not modified, whis notebook should produce a file identicle to our final kaggle submission.

res.py contains our implementation of a hidden Gaussian layer, which we moved around and tried to implement before deciding to set to zero for our final model submission (and thus returning to the keras-made API for final training.) This is just to show how we introduced such a layer.
