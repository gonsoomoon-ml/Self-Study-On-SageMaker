# ML OPs Step by Step

**마지막 업데이트: 2022.01.18**


---

# 1. 초급
### 1.1 [블로그, Apr 2020] [How Slalom and WordStream Used MLOps to Unify Machine Learning and DevOps on AWS](https://aws.amazon.com/blogs/apn/how-slalom-and-wordstream-used-mlops-to-unify-machine-learning-and-devops-on-aws/) 
   
- 요약
    - WordStream 회사가 AWS Service, Step Function, SageMaker 로 구성한 사례 임.
    - ML Ops 를 단계별로 접근하여 완성하는 모범적인 사례 임.
    - 전체 아키텍쳐의 구성을 위해서 아래 단계를 순서로 구현 함.
        - (1) Establish a data architecture
        - (2) Facilitate data analysis
        - (3) Enable rapid prototyping
        - (4) Productionize pipelines
        - (5) Deploy ML models
        - (6) Continuous improvement
- 구현 내용    
    - ![Slalom-Wordstream-ML-8.jpeg](img/Slalom-Wordstream-ML-8.jpeg)    
- 코드
    - 공개 되지 않음.

### 1.2 [워크샵, Apr 2021] [Amazon SageMaker Pipelines Getting Started](https://github.com/comeddy/amazon-sagemaker-mlops)
- 요약
    - SageMaker Pipeline Project 의 내장 템플릿을 사용하여 SageMaker Studio GUI 환경에서 코드 없이 클릭, 클릭으로 실습 해보는 내용 입니다. 처음 시작하는 입문용 입니다.  
    - 기본 내장 템블릿 "MLOps template for model building, training, and deployment" 을 구현 합니다.
    - 공식 개발자 가이드를 기본으 함. [SageMaker MLOps Project Walkthrough](https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-projects-walkthrough.html)
- 구현 내용    
    - ![SageMaker-Pipelines-Architecture.jpeg](img/youngjin.jpeg)    
- 코드
    - 실습 시간: 약 40 분
    - 위의 제목 링크

### 1.3 [블로그, Jan 2021] [Building, automating, managing, and scaling ML workflows using Amazon SageMaker Pipelines](https://aws.amazon.com/blogs/machine-learning/building-automating-managing-and-scaling-ml-workflows-using-amazon-sagemaker-pipelines/)
- 요약
    - SageMaker Pipeline Project의 기본 내장 템블릿 "MLOps template for model building, training, and deployment" 을 기반으로 사용자의 코드를 넣어서 만들어 보는 예시 입니다. 
- 구현 내용    
    - ![SageMaker-Pipelines-Architecture.jpeg](img/SageMaker-Pipelines-Architecture.jpeg)    
- 코드
    - 실습 시간: 약 1시간 
    - 블로그의 가이드 참조





