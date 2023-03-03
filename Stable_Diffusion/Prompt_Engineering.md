# SageMaker Stable Diffusion

**마지막 업데이트: 2023.02.21**


---
SageMaker Stable Diffusion 스스로 공부할 수 있는 링크 및 설명을 제공 합니다. 자세한 사항은 참조의 블로그 및 기타 링크를 확인 부탁 합니다.

---


guidance_scale: Higher guidance scale results in image closely related to the prompt, at the expense of image quality. If specified, it must be a float. guidance_scale<=1 is ignored.

The more it is the more closely it follows the prompt. However, after a certain value it becomes random. Think of it like weights for the prompt. Increasing guidance makes generation follow more closely to the prompt

negative_prompt: serves to specify what we don’t want to see in the image. For instance, if we want to generate an image with a cloudy sky, we enter clear sky as the negative prompt.
num_samples: the number of images the model will generate in a single batch.
guidance_scale: also known as CFG Scale, is a float that controls how much importance is given to the input text prompt. Lower values of this parameter will allow the model to take more artistic liberties when generating the images.
- https://tryolabs.com/blog/2022/10/25/the-guide-to-fine-tuning-stable-diffusion-with-your-own-images

