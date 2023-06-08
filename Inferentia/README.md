# Inferentia : Self-Study-On-SageMaker

**마지막 업데이트: 2023.06.08**


---

# 1. Inferentia 공식 개발자 문서

* AWS Neuron SDK
    * 공식 Neuron SDK 개발 문서이며, Get Started with PyTorch / TensorFlow 를 진행 해보시기 바랍니다.
    * https://awsdocs-neuron.readthedocs-hosted.com/en/latest/index.html
* The AWS Inferentia Chip With DLAMI
    * EC2 DLAMI 를 이용하여 실습을 위한 문서 
        * https://docs.aws.amazon.com/dlami/latest/devguide/tutorial-inferentia.html
    * 참고: Running Jupyter Notebook Tutorials with DLAMI
        * https://docs.aws.amazon.com/dlami/latest/devguide/tutorial-jupyter.html    
* Neuron SDK Roadmap
    * 공식적인 Neuron SDK 의 현재 지원 내용 및 추후 개발 내용이 있습니다. 현재 가지고 있는 모델의 Neuron 제공 여부를 확인할 수 있습니다.
    * new: https://github.com/orgs/aws-neuron/projects/1
        - old: https://github.com/aws/aws-neuron-sdk/projects/2?fullscreen=true
* AWS Neuron Forum
    * Neuron 에 대한 질의 및 응답
    * https://github.com/aws-samples/aws-do-inference
* Optimize model performance using Neo
    * SageMaker Neo 의 공식 개발자 가이드, Neo  로 컴파일한 후에 SageMaker Inference 하기
    * https://docs.aws.amazon.com/sagemaker/latest/dg/neo.html

# 2. 처음 시작하기 

- AWS Inferentia Overview (Neuron SDK 1.18.0)
    * 김대근님이 Inferentia 오버뷰를 한글로 정리
    * https://daekeun.notion.site/AWS-Inferentia-Overview-Neuron-SDK-1-18-0-d07761f3ef02489f8dad4814fcba6da3
    
   
# 3. 모델 컴파일
- 간단한 컴파일 예시 
    - [PyTorch Neuron (torch-neuronx) Tracing API for Inference](https://github.com/aws-samples/aws-ai-ml-workshop-kr/tree/master/sagemaker/recommendation/Neural-Collaborative-Filtering-On-SageMaker/2_Trn1_Inf2)
- 나의 모델이 Neuron SDK 에서 지원 하는지 (컴피일 가능) 확인 하기
    - 상세 보기 : [Check-Model](README-CheckModel.md)

# 4. Example Code


* Inferentia2 로 추천 모델 (Neural Collaborative Filtering) 을 컴파일 및 서빙 예시 입니다.
    - [추천 모델 INF2 로 모델 서빙](https://github.com/aws-samples/aws-ai-ml-workshop-kr/tree/master/sagemaker/recommendation/Neural-Collaborative-Filtering-On-SageMaker/2_Trn1_Inf2)
* 아래는 인퍼런시아 워크샵 링크 입니다.  단계별로 Tensorflow 로 ResNet-50  을 Pytorch 로 BERT 를 컴파일, 추론, 서빙, 툴 소개를 하고 있습니다.
    * 현재 영어 버전의 링크가 연결이 안됩니다. 일본어 버전을 “크롬” 에서 한글로 번역하면서 보시기를 권장 합니다. 
        * [Chrome 언어 변경 및 웹페이지 번역](https://support.google.com/chrome/answer/173424?hl=ko&co=GENIE.Platform%3DDesktop)
    * Amazon EC2 Inf1 Workshop
        * https://catalog.us-east-1.prod.workshops.aws/workshops/bcd3db22-8501-4888-a078-45a70034f802/en-US
        * 일본어
            * https://dcj71ciaiav4i.cloudfront.net/DF2C2C00-CD94-11EB-9681-5F0F8AE2FC7B/
        * 영어
            * 링크 연결 안됨.

- Amazon SageMaker Neo Compilation Jobs
    * SageMaker 에서 Neuron Compile
    * https://github.com/aws/amazon-sagemaker-examples/tree/main/sagemaker_neo_compilation_jobs
- CMP314 Optimizing NLP models with Amazon EC2 Inf1 instances in Amazon Sagemaker
    - https://github.com/aws-samples/aws-inferentia-huggingface-workshop
- AWS re:Invent 2021 Inferentia Workshop
    - * https://github.com/aws-samples/aws-reinvent21-inf1-workshop
- Inference workload deployment sample with optional bin-packing
    - * https://github.com/aws-samples/aws-do-inference



# 5. 블로그 및  YouTube

- [강추, 스캐터랩 작성] AWS Inferentia 를 이용한 모델 서빙 비용 최적화: 모델 서버 비용 2배 줄이기 1탄 (July 2022)
    * https://blog.pingpong.us/aws-inferentia/
- AWS Supports You | Using AWS Inferentia and Trainium in Practice (Jun 2022)
    - * https://www.youtube.com/watch?v=HYnVeLmAsZ0
- How InfoJobs (Adevinta) improves NLP model prediction performance with AWS Inferentia and Amazon SageMaker (Jun 2022)
    * https://aws.amazon.com/blogs/machine-learning/how-infojobs-adevinta-improves-nlp-model-prediction-performance-with-aws-inferentia-and-amazon-sagemaker/
- Achieve hyperscale performance for model serving using NVIDIA Triton Inference Server on Amazon SageMaker (May 2022)
    * https://aws.amazon.com/blogs/machine-learning/achieve-hyperscale-performance-for-model-serving-using-nvidia-triton-inference-server-on-amazon-sagemaker/
- How Amazon Search achieves low-latency, high-throughput T5 inference with NVIDIA Triton on AWS (Mar 2022)
    * https://aws.amazon.com/blogs/machine-learning/how-amazon-search-achieves-low-latency-high-throughput-t5-inference-with-nvidia-triton-on-aws/
- Accelerate BERT inference with Hugging Face Transformers and AWS Inferentia (Mar 2022)
    * https://huggingface.co/blog/bert-inferentia-sagemaker
- Serve 3,000 deep learning models on Amazon EKS with AWS Inferentia for under $50 an hour (Sep 2021)
    * https://aws.amazon.com/blogs/machine-learning/serve-3000-deep-learning-models-on-amazon-eks-with-aws-inferentia-for-under-50-an-hour/
- Achieving 1.85x higher performance for deep learning based object detection with an AWS Neuron compiled YOLOv4 model on AWS Inferentia (Oct 2020)
    * https://aws.amazon.com/blogs/machine-learning/improving-performance-for-deep-learning-based-object-detection-with-an-aws-neuron-compiled-yolov4-model-on-aws-inferentia/
- Deploying TensorFlow Models on AWS Inferentia Based Inf1 Instances with Amazon SageMaker (July 2020)
    - * https://www.youtube.com/watch?v=u3oFpjq0ciY
- Deploying TensorFlow OpenPose on AWS Inferentia-based Inf1 instances for significant price performance improvements (Jul 2020)
    - * https://aws.amazon.com/blogs/machine-learning/deploying-tensorflow-openpose-on-aws-inferentia-based-inf1-instances-for-significant-price-performance-improvements/


# 6. 기타 인퍼런스 자료
- Deploy fast and scalable AI with NVIDIA Triton Inference Server in Amazon SageMaker
    - https://aws.amazon.com/blogs/machine-learning/deploy-fast-and-scalable-ai-with-nvidia-triton-inference-server-in-amazon-sagemaker/

