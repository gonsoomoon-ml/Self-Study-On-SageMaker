# How to fine-tune

**마지막 업데이트: 2023.03.03**


---
    

# 1. Stable Diffusion 파인 튜닝.

## 1.1 How fine-tunig works

A Stable Diffusion model can be decomposed into several key models:
* A text encoder that projects the input prompt to a latent space. (The caption associated with an image is referred to as the "prompt".)
* A variational autoencoder (VAE) that projects an input image to a latent space acting as an image vector space.
* A diffusion model that refines a latent vector and produces another latent vector, conditioned on the encoded text prompt
* A decoder that generates images given a latent vector from the diffusion model.
- **It's worth noting that during the process of generating an image from a text prompt, the image encoder is not typically employed.**
 

The process of fine-tuning
* An input text prompt is projected to a latent space by the text encoder.
* An input image is projected to a latent space by the image encoder portion of the VAE.
* A small amount of noise is added to the image latent vector for a given timestep.
* The diffusion model uses latent vectors from these two spaces along with a timestep embedding to predict the noise that was added to the image latent.
* A reconstruction loss is calculated between the predicted noise and the original noise added in step 3.
* Finally, the diffusion model parameters are optimized w.r.t this loss using gradient descent.
- **Note that only the diffusion model parameters are updated during fine-tuning, while the (pre-trained) text and the image encoders are kept frozen.**
    
- Ref: [Fine-tuning Stable Diffusion](https://keras.io/examples/generative/finetune_stable_diffusion/)

## 1.2 파인 튜닝 Tips
* 파인 튜닝 방법
Once you’ve collected these images, the next step is to label them with a text prompt. Following the instructions in DreamBooth’s paper, we’ll use the prompt A [token name] [class noun] where [token name] is an identifier that will reference us, and [class noun] is an already existing class in the model’s vocabulary which describes us at a high level. For instance, for Fernando Bernuy (co-writer and one of the victims of our experiment), a possible prompt would be A fbernuy man. Other examples of class nouns include woman, child, teenager, dog, or sunglasses. Yes, this approach works with animals and other objects too!
```
# replace the instance_prompt parameter to our token name:
--instance_prompt=="photo of fbernuy george clooney"

# check that the class_prompt is set as:
--class_prompt="photo of {CLASS_NAME}"

# set:
--num_class_images=200
--max_train_steps=2400
--gradient_accumulation_steps=2
--lerning_rate=1e-6
```
- Ref: [The guide to fine-tuning Stable Diffusion with your own images](https://tryolabs.com/blog/2022/10/25/the-guide-to-fine-tuning-stable-diffusion-with-your-own-images)


