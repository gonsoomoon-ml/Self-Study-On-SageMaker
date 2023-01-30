# Training : Self-Study-On-SageMaker

**마지막 업데이트: 2023.01.30**


---

# 1. 세이지 메이커의 훈련 개요
![SM-Training-Methods.png](img/SM-Training-Methods.png)



# 2. 세이지 메이커의 스크립트 모드 (Bring Your Own Script, BYOS)
- TBD
- 로컬 모드 사용시에 다커의 위치 변경 및 Shared Memory 사이즈 변경
    - [로컬 모드 셋업 가이드](../workaround/sagemaker_classic_nb_localmode-shm_error.md)

# 3. 세이지 메이커의 사용자 정의 컨테이너 (Bring Your Own Container, BYOC)

## 3.1 처음 시작하기
- 세이지메이커에서 도커 컨테이너 사용
    - [공식 기발자 가이드](https://docs.aws.amazon.com/ko_kr/sagemaker/latest/dg/docker-containers.html)
- BYOC 기본 설명
    - [요약정리](https://github.com/gonsoomoon-ml/churn-prediction-workshop2/tree/master/BYOC)
* 기본 BYOC 작성 코드 예시
    * https://github.com/aws-samples/aws-ai-ml-workshop-kr/tree/master/sagemaker/byoc


## 3.2 BYOC 실무 적용하기

* BYOC를 만드는 방법이 크게 4가지가 있습니다. (Basic, Script Mode1, 2 , Framework)
    * Basic 으로 컨테이너를 생성하면, 훈련 코드(예: train.py) 가 컨테이너에 같이 포함되어서 생성이 되기에, 매번 수정이 되면 다커를 다시 빌딩하고 ECR에 등록해야 하는 과정을 거칩니다.
    * *Script Mode, Framework 방식을 사용하면 훈련 코드를 정적으로 다커에 포함하지 않고, 훈련시만 지정해서 사용 가능 합니다. 매번 다커 빌딩 및 ECR 푸시할 필요가 없습니다. 이것 테스트 해보시면 좋겠습니다. *
        * Framework 혹은 Script Mode2 추천
    * Amazon SageMaker Custom Training containers 만드는 4가지 방식
        * https://github.com/aws/amazon-sagemaker-examples/tree/master/advanced_functionality/custom-training-containers
        * Framework Container 만든는 예제 코드
            * https://github.com/aws/amazon-sagemaker-examples/tree/main/advanced_functionality/custom-training-containers/framework-container


## 3.3 훈련 유스 케이스 코드
* Fsx Luster 를 통한 BYOC 를 통한 학습 (Distributed Training of Mask-RCNN in Amazon SageMaker using FSx)
    - 아래 README 에서 New SageMaker Notebook in VPC 메뉴를 통해 VPC 생성
        - https://github.com/aws/amazon-sagemaker-examples/tree/main/advanced_functionality/distributed_tensorflow_mask_rcnn
    - 아래 Distributed Training of Mask-RCNN in Amazon SageMaker using FSx 노트북을 실행
        - https://github.com/aws/amazon-sagemaker-examples/blob/main/advanced_functionality/distributed_tensorflow_mask_rcnn/mask-rcnn-scriptmode-fsx.ipynb

## 3.4 관련 블로그 및 자료
* [강추] Choose the best data source for your Amazon SageMaker training job (Feb 2022)
    - 훈련을 할시에 여러가지 데이터 소스(s3, Fsx Luster, EFS 등 설명) 특장점 및 선택 방법 가이드
    - https://aws.amazon.com/blogs/machine-learning/choose-the-best-data-source-for-your-amazon-sagemaker-training-job/
    - ![ML-2979-image003.png](img/ML-2979-image003.png)

- 아래 블로그는 BYOC 에 대한 엔드 투 엔드 쉽게 설명을 하고 있습니다. 전체적인 관점에서 정리하는데 유용합니다.
    - [(Jan 2023) Why Bring Your Own Container to Amazon SageMaker and How to do it right !](https://medium.com/@pandey.vikesh/why-bring-your-own-container-to-amazon-sagemaker-and-how-to-do-it-right-bc158fe41ed1)

## 3.5 SageMaker Toolkit

- SageMkaer 는 4개의 Traiing Toolkit, 4개의 Inference Toolkit 을 제공하고 있습니다. 이를 이행하고 있으면, 훈련 및 추론의 디벌깅 및 코드의 간결화에 도움이 됩니다.
    - [Jan 203, The Multiverse of Amazon SageMaker Toolkits](https://medium.com/@pandey.vikesh/the-multiverse-of-amazon-sagemaker-toolkits-7560c2b0f0b6)

# 4. 하이퍼파라미터 튜닝 통한 모델 최적화
## 4.1 개발자 가이드
- [HPO 개발자 기이드](https://docs.aws.amazon.com/ko_kr/sagemaker/latest/dg/automatic-model-tuning-how-it-works.html)
- [SageMaker Python SDK, HPO](https://sagemaker.readthedocs.io/en/stable/api/training/tuner.html)

## 4.2 블로그
- Running multiple HPO jobs in parallel on Amazon SageMaker (Feb 2021)
    - https://aws.amazon.com/ko/blogs/machine-learning/running-multiple-hpo-jobs-in-parallel-on-amazon-sagemaker/
    - ![Batching-HPO-Pipeline.jpg](img/Batching-HPO-Pipeline.jpg)

## 4.3 샘플 코드    
- [SageMaker Example, HPO](https://github.com/aws/amazon-sagemaker-examples/tree/main/hyperparameter_tuning)
- [XGBoost HPO](https://github.com/gonsoomoon-ml/SageMaker-Pipelines-Step-By-Step/blob/main/phase01/3.1.HPO-Pipeline.ipynb)
    - 간단하게 HPO 실행결과 확인 하시고, 필요하시면 딥 다이브 하세요.

# 5. SageMaker Clarify
- [상세 가이드](SMClarify.md)
