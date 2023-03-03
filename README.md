# Masked-Autoencoders_Vision
Overview and discussion of Masked Autoencoders Are Scalable Vision Learners (He et al. 2021) 
EDITING HELP (https://stackoverflow.com/questions/11509830/how-to-add-color-to-githubs-readme-md-file)
## Background
+ Masked autoencoding: removes a portion of the data so the model can learn to predict the removed information. Masked auto encoding has been successfully applied to train generalizable NLP models. The authors, He and colleagues, argue that masked autoencoders are as applicable to computer vison. 
+ Why has Masked autoencoding been applied to vison before? Vision architecture used to be predominantly convolutional neural networks (CNN), which made integrating mask tokens and positional embeds more difficult.
   + That changed with Vision Transformers (ViT)! 
   + Transformer architecture only- Applying mask tokens and positional embeds more feasible. 

## Research Question
+ what makes masked autoencoding different
between vision and language?
## Approach 
+ Novelty of approach is masking of images: masking random patches from the image and feeding the transformer an incomplete image. 
+ How? 2 key parts to training to achieve self supervised learning with MAE:
  + Assymetric encoder-decoder architecture where the encoder operates on the patches without mask tokens (below we see the patches with the flamingo visible are going into the encoder)
  + Masking a large portion of the image 

## Architecture Overview
+ (https://github.com/facebookresearch/mae/blob/main/models_mae.py)
+ 
![image](https://user-images.githubusercontent.com/80427603/222825277-991b51be-050f-4fa6-a72d-2e7dbc30cde9.png)

## Results

## Code Demo time!
+ The two senior authors created a repo with this demo (https://colab.research.google.com/drive/1NXe-zBSYKZTDugepN9_uFRDT8Ti708Vk#scrollTo=4573e6be-935a-4106-8c06-e467552b0e3d)

## Discussion Questions
+ Question 1:
+ Question 2:

## Critical Analysis

## Key Takeaways

## Resources 
+ This is a link to a Chen and He's repo on Github: (https://github.com/facebookresearch/mae)
+ ViT paper: An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale (https://arxiv.org/abs/2010.11929)

## Questions?
