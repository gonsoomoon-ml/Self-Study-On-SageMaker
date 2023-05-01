
# SageMaker-Distributed-Training-Resource
---

**마지막 업데이트: 2023.05.01**

# 0. FSx for Luster 설치 가이드
- [aker Notebook 및 FSX for Luster 생성 가이드](https://github.com/gonsoomoon-ml/FSx-Luster-On-SageMaker/blob/main/0_setup_environment/1.VPC_SM_Notebook/README.md)

# 1. Video:

(강력 추천) Amazon SageMaker를 통한 딥러닝 분산 학습 및 디버거 프로파일링 활용하기 – 최영준:: AWS Innovate 2021 (30 분)

* https://www.youtube.com/watch?v=lsTtoACAPj4

AWS re:Invent 2020: Fast training and near-linear scaling with DataParallel in Amazon SageMaker (30분)

* https://www.youtube.com/watch?v=EXmz5g8F2zU

AWS re:Invent 2020: Train billion-parameter models with model parallelism on Amazon SageMaker (30분 소요)

* https://www.youtube.com/watch?v=vv52RsBM8o4

AWS on Air 2020: AWS What’s Next ft. new libraries for distributed training on Amazon SageMaker (31분 소요)

* https://www.youtube.com/watch?v=nz1EwsS5OiA

Scale up Training of Your ML Models with Distributed Training on Amazon SageMaker (Sep 2019)

* 기본적인 분산 훈련의 개념을 소개 (15분 소요)

* https://www.youtube.com/watch?v=CDg55-GkIm4&list=PLhr1KZpdzukcOr_6j_zmSrvYnLUtgqsZz&index=8



# 2. Blog:  발행 시간 순으로 정렬 함.

- (Jan 2023) 스텝 바이 스텝으로 BERT 를 세이지 메이커로 스크래치부터 훈련하는 가이드 입니다. 
    - [­­­Training BERT from Scratch on Your Custom Domain Data: A Step-by-Step Guide with Amazon SageMaker](https://medium.com/@shankar.arunp/training-bert-from-scratch-on-your-custom-domain-data-a-step-by-step-guide-with-amazon-25fcbee4316a)
- (Jan 2023) 세이지 메이커 기반에서 “스크래치” 부터 GPT 를 학습하는 블로그 입니다. 고객들의 해당 도메인에서 해볼 수 있게 가이드 입니다. 
    - [Easily Build Your Own GPT from Scratch using AWS: A Comprehensive Guide for Domain Adaptation](https://medium.com/@shankar.arunp/easily-build-your-own-gpt-from-scratch-using-aws-51811b6355d3)

* Amazon SageMaker Simplifies Training Deep Learning Models With Billions of Parameters (Dec 2020)
    * https://aws.amazon.com/ko/blogs/aws/amazon-sagemaker-simplifies-training-deep-learning-models-with-billions-of-parameters/
* New – Data Parallelism Library in Amazon SageMaker Simplifies Training on Large Datasets (Dec 2020)
    * https://aws.amazon.com/ko/blogs/aws/managed-data-parallelism-in-amazon-sagemaker-simplifies-training-on-large-datasets/
* New – Profile Your Machine Learning Training Jobs With Amazon SageMaker Debugger (Dec 2020)
    * https://aws.amazon.com/ko/blogs/aws/profile-your-machine-learning-training-jobs-with-amazon-sagemaker-debugger/
* How Latent Space used the Amazon SageMaker model parallelism library to push the frontiers of large-scale transformers (Mar 2020)
    * https://aws.amazon.com/ko/blogs/machine-learning/how-latent-space-used-the-amazon-sagemaker-model-parallelism-library-to-push-the-frontiers-of-large-scale-transformers/
* Distributed Training: Train BART/T5 for Summarization using 🤗 Transformers and Amazon SageMaker (Apr 2021)
    * https://huggingface.co/blog/sagemaker-distributed-training-seq2seq
* Multi-GPU distributed deep learning training at scale with Ubuntu18 DLAMI, EFA on P3dn instances, and Amazon FSx for Lustre (Jun 2020)
    * https://aws.amazon.com/blogs/machine-learning/multi-gpu-distributed-deep-learning-training-at-scale-on-aws-with-ubuntu18-dlami-efa-on-p3dn-instances-and-amazon-fsx-for-lustre/
* (강추) Hyundai reduces ML model training time for autonomous driving models using Amazon SageMaker (Jun 2021)
    * https://aws.amazon.com/ko/blogs/machine-learning/hyundai-reduces-training-time-for-autonomous-driving-models-using-amazon-sagemaker/


* [강추] Choose the best data source for your Amazon SageMaker training job (Feb 2022)
    - 훈련을 할시에 여러가지 데이터 소스(s3, Fsx Luster, EFS 등 설명) 특장점 및 선택 방법 가이드
    - https://aws.amazon.com/blogs/machine-learning/choose-the-best-data-source-for-your-amazon-sagemaker-training-job/


- Transfer Learning with Amazon SageMaker and FSx for Lustre (Feb 2022)
    * 샘플 코드는 제공을 안하나 전체적인 가이드를 제공 하고 있음.
    * https://medium.com/@sayons/transfer-learning-with-amazon-sagemaker-and-fsx-for-lustre-378fa8977cc1

# 3, 개발자 가이드:

SageMaker Distributed Training

* https://docs.aws.amazon.com/ko_kr/sagemaker/latest/dg/distributed-training.html



# 4. 코드

아마존 세이지메이커 예제 (공식 예제)

* https://github.com/aws/amazon-sagemaker-examples/tree/master/training
* 한글 번역
    * https://github.com/daekeun-ml/sagemaker-distributed-training


TensorFlow 

* SageMaker-Tensorflow-Step-by-Step 워크샵 
    * 세이지 메이커 TF Getting Started, Horovod, Data Distributed Parallelism 포함
    * https://github.com/gonsoomoon-ml/SageMaker-Tensorflow-Step-By-Step
* SageMaker Debugger, Profiler, and Data Distributed Parallelism
    *  https://github.com/daekeun-ml/sagemaker-distributed-training-tf2


PyTorch 예제 

* SageMaker-PyTorch-Step-By-Step
    * 세이지 메이커 Pytorch Getting Started, Horovod, Data Distributed Parallelism 포함
    * https://github.com/gonsoomoon-ml/SageMaker-PyTorch-Step-By-Step
* Oxford-IIT Pet Dataset 사용하여 Data Distributed Parallelism 
    * https://github.com/aws-samples/sagemaker-distributed-training-pytorch-kr



# 4. 컨퍼런스 및 기타

* Distributed Training with TensorFlow on AWS
    * https://github.com/shashankprasanna/distributed-training-workshop/blob/master/static/tf-world-distributed-training-workshop.pdf
* *SageMaker Prep Data (Image, Tabular, Text)*
    * https://github.com/aws/amazon-sagemaker-examples/tree/master/prep_data
* Accelerate computer vision training using GPU preprocessing with NVIDIA DALI on Amazon SageMaker

    * https://aws.amazon.com/ko/blogs/machine-learning/accelerate-computer-vision-training-using-gpu-preprocessing-with-nvidia-dali-on-amazon-sagemaker/

