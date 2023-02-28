# Masked-Autoencoders_Vision
Overview and discussion of Masked Autoencoders Are Scalable Vision Learners (He et al. 2021) 
EDITING HELP (https://stackoverflow.com/questions/11509830/how-to-add-color-to-githubs-readme-md-file)
## Background

## Research Question
+ what makes masked autoencoding different
between vision and language?
## Approach 
+ Novelty of approach is masking of images: masking random patches from the image and feeding the transformer an incomplete image. 
+ How?
  + Assymetric encoder-decoder architecture where the encoder operates on the patches without mask tokens (below we see the patches with the flamingo visible are going into the encoder)
  + 
![image](https://user-images.githubusercontent.com/80427603/221093069-6d8bdb6e-1a77-45c3-ba35-6b4970a8bb0a.png)

## Architecture Overview/ Pseudocode
+ (https://github.com/facebookresearch/mae/blob/main/models_mae.py)
## Code Demo time!
+ The two senior authors created a repo with this demo (https://colab.research.google.com/github/facebookresearch/mae/blob/main/demo/mae_visualize.ipynb)

## Results

## Discussion Questions
+ Question 1:
+ Question 2:

## Critical Analysis

## Key Takeaways

## Resources 
+ This is a link to a Chen and He's repo on Github: (https://github.com/facebookresearch/mae)
