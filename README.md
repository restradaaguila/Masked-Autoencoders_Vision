# Masked-Autoencoders_Vision
Overview and discussion of Masked Autoencoders Are Scalable Vision Learners (He et al. 2021) 
EDITING HELP (https://stackoverflow.com/questions/11509830/how-to-add-color-to-githubs-readme-md-file)

## Background
+ Autoencoders- technique that uses encoder-decoder architecture to  learn how to compress and reconstruct data. It is mainly used for unsupervised learning.  
   + Computer vision: autoencoding can be used to remove noise from images, generate new images, or find hidden patterns in images.
+  Masked autoencoding: removes a portion of the data so the model can learn to predict the removed information. Masked auto encoding has been successfully applied to train generalizable NLP models. The authors, He and colleagues, argue that masked autoencoder models can be succesfully applied to computer vison. 

## Research Question
+ What makes masked autoencoding different
between vision and language? 
   + Architecture
      +  Vision architecture used to be predominantly convolutional neural networks (CNN), which made integrating mask tokens and positional embeddings more difficult.
            + That changed with Vision Transformers (ViT)! 
            + Transformer architecture- Applying mask tokens and positional embeds more feasible. 
   +  Information density
      + Language is information dense and packed with meaning- masking a few word is enough of a challenge 
      + Images are heavy in spatial redundancy- masking high proportions of image reduces redundancy and presents a more challenging task. 
     
    75% Masking

 ![image](https://user-images.githubusercontent.com/80427603/223315668-91c9904a-bca2-4db8-b4bf-c75a36747ffb.png)

 ![image](https://user-images.githubusercontent.com/80427603/223315736-a4105bd6-137f-4544-8028-7d854ee7021e.png)

+ What is the best performing method for vision
## Approach 
+ Novelty of approach is masking of images: masking random patches from the image and feeding the transformer an incomplete image. 
+ How? 2 key parts to training to achieve self supervised learning with MAE:
  + Assymetric encoder-decoder architecture
  + Masking a large portion of the image is the most effective to learning
+ Pre-processing 
   + Masking large portion is the most effective- 75% of image is masked
      + faster training (3x faster) than a whole image
      + increase in image reconstruction accuracy
     ![image](https://user-images.githubusercontent.com/80427603/223297608-737e9c39-36ea-4519-87e0-845747f85ef4.png)
 
   + Masking is applied randomly- image can be input multiple times

## Architecture Overview
+ (https://github.com/facebookresearch/mae/blob/main/models_mae.py)
+ Assymetrical encoder-decoder architecture
+ Encoder
   + Divides image into pateches assigned positional encodeings 
   Encoder operates on the patches without mask tokens (below we see the patches with the flamingo visible are going into the encoder)
   + Output is a latent vector representation 
   Positional encodings to communicate location of each square in the input image
+ Decoder
   + 
   + Outputs pixel values for masked and unmasked patches.
   + Full input image is reconstructed with predicted pixel values for masked squares. 
+ Differences between input image and reconstruction are measured and used as loss
+ After pre-training- decoder is discarded and encoder is kept for fine tuning

Question 1: Why throwaway the decoder? Why is it no longer needed?
   
   ![image](https://user-images.githubusercontent.com/80427603/222825277-991b51be-050f-4fa6-a72d-2e7dbc30cde9.png)

## Results
Image with mask tokens, reconstructed image, original image

![image](https://user-images.githubusercontent.com/80427603/223009216-00b5c5a3-597b-4224-8e5f-bbb50080c8fe.png)

![image](https://user-images.githubusercontent.com/80427603/223009302-ad59be13-7681-4f59-8e22-be8c309f39a5.png)

+ Performance of MAE is compared to other self-supervised transformer models: DINO, MoCov3 and BEiT
   + MAE is the most accurate!
![image](https://user-images.githubusercontent.com/80427603/223008783-5d9403c8-cfe4-4dd4-a897-c2388ee8ae76.png)

## Code Demo time!
+ The two senior authors created a repo with this demo (https://colab.research.google.com/drive/1NXe-zBSYKZTDugepN9_uFRDT8Ti708Vk#scrollTo=4573e6be-935a-4106-8c06-e467552b0e3d)

## Critical Analysis

## Key Takeaways

## Resources 
+ This is a link to a Chen and He's repo on Github: (https://github.com/facebookresearch/mae)
+ ViT paper: An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale (https://arxiv.org/abs/2010.11929)
+ Vison transformers compared in paper: DINO (https://arxiv.org/abs/2104.14294) MoCov3 (https://paperswithcode.com/method/moco-v3) BEiT (https://arxiv.org/abs/2106.08254)

## Questions?
