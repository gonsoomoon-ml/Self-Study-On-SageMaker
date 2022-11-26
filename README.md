# Self-Study-On-SageMaker

**마지막 업데이트: 2022.11.26**

### 컨텐츠 레벨 가이드:
    - 일부 컨텐츠는 레벨 가이드가 있습니다.
    - <Level 100-200>: 초급
    - <Level 200-300>: 중급
    - <Level 300-400>: 고급    
    
### 신규 컨텐츠:
- <font color="green">[Hot Update]</font> <Level 200-300> 2022 AWS Seoul Summit
    - 80+ 세션 (SageMaker 세션은 아래 "3. AWS AI/ML 리소스 허브, 특집 이벤트 및 AWS ML 전문가 링크" 참고 하세요.) --> [전체 세션 목록](https://m.youtube.com/playlist?list=PLORxAVAC5fUX7j65Uvp9xAi1hMS6M-2P1)
- <font color="green">[Hot Update]</font> <Level 200-400> 2022 AWS AIML 스페셜 웹비나
    - 12+ 세션 (SageMaker, Personalize)
        - SageMaker 는 초급/중급 수준의 SageMaker 입문, 모델 훈련, 배포 및 추론, ML Ops (SageMaker Pipeline) 에 대한 모듈별 비디오가 있습니다.
        - [전체 세션 목록](https://www.youtube.com/playlist?list=PLORxAVAC5fUULZBkbSE--PSY6bywP7gyr)
- <font color="green">[Hot Update]</font> <Level 200-300> AWS 머신 러닝 블로그를 전문가가 설명해주기:   --> [10분만에 따라잡는 AWS 머신러닝](https://www.youtube.com/playlist?list=PLORxAVAC5fUW3U4KlNCg7BNctpJMMjUV8)






---

**이 문서의 목적은  혼자 SageMaker 의 학습을 하기 위한 자료 및 링크가 있습니다. 아래와 같은 큰 목차에 관련 정보가 있으니 참고 하세요.**

- [알림] 아래 링크는 깃 리파지토리를 다운로드 하시고 README 파일을 열고 클릭시 작동 됩니다. 웹페이지에서 보실때는 스크롤다운해서 확인 바랍니다.

- [1. SageMaker 선수 지식 및 101](#1.-SageMaker-선수-지식-및-101)
- [2. SageMaker 입문](#2.-SageMaker-입문)
- [3. AWS AI/ML 리소스 허브, 특집 이벤트 및 AWS ML 전문가 링크
](#3.-특집-이벤트)
- [4. SageMaker 기본](#4.-SageMaker-기본)
- [5. 유용한 자료 (백서 등)](#5.-유용한-자료-(백서-등))
- [6. 체계적인 교육](#6.-체계적인-교육)
- [7. 아마존 사이언스 및 최신 ML 트랜드](#7.-아마존-사이언스)


- 8.세이지 메이커 상세 및 기타 지식 입니다. [아래 링크 제공 됨. 클릭 하세요.]
    - [SageMaker 개발 환경](Environment/README.md)
    - [SageMaker 훈련](Training/README.md)
    - [SageMaker 분산 훈련](DistributedTraining/README.md)        
    - [SageMaker 추론](Inference/README.md)            
    - [Inferentia 추론](Inferentia/README.md)                
    - [ML Ops on SageMaker](MLOps/README.md)    
    - [SageMaker Vision](Vision/README.md)                   
    - [SageMaker NLP](NLP/README.md)               
    - [SageMaker RL, 강화학습](RL/README.md)           
    - [유용한 트러블 슈팅](workaround/README.md)
    - [세이지 메이커 유용한 명령어](UsefulCommand/README.md)    
    - [세이지 메이커 비용 최적화](Cost_Optimization/README.md)
    - [Tabular 데이터 피쳐 선택 가이드](data_preparation/Feature_Selection_Guide.md)

    



## 1. SageMaker 선수 지식 및 101
---

* AWS Cloud 일반 지식 (S3, EC2, IAM 등) (초급/중급 정도 수준)

* Python 코딩 (Pandas, Numpy 패키지 초급/중급 정도 수준)

* SageMaker Video 비디오
    * 2020년 9월 버전 (1분 40초) -->  [간단소개](https://www.youtube.com/watch?v=EhExK4JgXvE)
    - 2021년 2월 버전 (4분 46초) --> [Introduction to Amazon SageMaker](https://www.youtube.com/watch?v=Qv_Tr_BCFCQ)



* AWS SageMaker 공식 웹 사이트
    * **이것은 자주 봐야할 곳 입니다. 처음에는 간단히 보시기 바랍니다.**
    * 전반적인 소개 및 가능한 다양한 리소스 정보를 접할 수 있습니다. 
    * https://aws.amazon.com/ko/sagemaker/
    
    
* 쥬피터 노트북 1회 실행 (아래에서 1개만 수행하시면 됩니다.)
    * SageMaker 10분 튜토리얼
        * 세이지 메이커 콘솔에서 노트북 인스턴스를 설치하고, 제공된 파이썬 코드를  Copy & Paste를 하면 모델 빌딩, 구축, 배포를 확인할 수 있습니다. 코드의 이해는 일단 지나치시고, 전체적으로 동작하는 원리만 아는 것으로 초점을 맞추어 주세요.
        * 아래를 진행할 시에 리젼은 us-west-2, us-east-1, us-east-2, eu-west-1 중에 하나를 선택해야 합니다. : 빌트인 내장 알고리즘 컨테이너를 위 리젼에서 가져옴
            * https://github.com/comeddy/Start-SageMaker 
    * 다른 노트북 인스턴스 사용 예제
        * Amazon SageMaker 노트북 인스턴스 사용
        * https://docs.aws.amazon.com/ko_kr/sagemaker/latest/dg/nbi.html
    
    
* AWS 기계 학습 교육 공식 웹사이트 
    * **이것은 자주 봐야할 곳 입니다. 지금은 스킵 하셔도 됩니다.**
    - **개발자, 데이터 사이언티스트, 데이터 플랫폼 엔지니어, 비즈니스 의사 결정권자" 의 역할 별로 강좌가 준비되어 있습니다.** 
    - 기계 학습(ML), 인공 지능(AI), 딥러닝(DL)을 비즈니스에 적용하여 새로운 인사이트와 가치를 창출하는 방법을 배웁니다. ML을 활용하여 Amazon에서 해결한 문제를 바탕으로 실제 사례를 살펴보고 실습을 수행합니다. 다수가 무료로 제공되는 65여 개 과정을 이용할 수 있습니다.
    - https://aws.amazon.com/ko/training/learn-about/machine-learning/
* 머신 러닝 기본 (기타 자료를 보셔도 됩니다.)
    - AWS AI/ML Expert 김성민님의 1시간 머신러닝 개념 잡기 입니다.
        - [1시간 만에 머신 러닝 개념 따라 잡기](https://www.youtube.com/watch?v=cYI85HFgFeg)
    * 생활 코딩: 머신러닝 
        * https://opentutorials.org/course/4548
        
        
* 다커 컨테이너 동작 방식 - **이것은  옵션 입니다. 지나 치셔도 됩니다.**
    * Hello Docker
        * https://github.com/mullue/hello-docker


## 2. SageMaker 입문 
---

**목표: 세이지 메이커의 기본 구조와 사용법 알기**

* SageMaker 소개 유튜브 비디오 (한글)
    * 세이제 메이커 예제 싥습과 함께 전반적인 소개를 합니다.
        - [SageMaker Overview](https://youtu.be/jF2BN98KBlg)
    - 전반적인 기본 컨셉 및 세이지 메이커 전반을 설명 합니다.
        - [Amazon SageMaker 통해 머신러닝 시작하기](https://www.youtube.com/watch?v=6sdr6dViK2U)
    * SageMaker demo - https://youtu.be/miIVGlq6OUk (1시간 데모에 많은 내용을 압축해서 다루고 있습니다. 반복해서 보시거나 돌려보기로 차근차근 보셔도 괜찮습니다.)
* Introduction to Amazon SageMaker (12분)
    * 코세라 공식 세이지 메이커 소개 비디오
    * https://www.coursera.org/lecture/aws-machine-learning/introduction-to-amazon-sagemaker-QugTh


* Amazon SageMaker Deep Dive Series **(아래 두개만 일단 보셔도 됩니다. 각 비디오가 약 10-20분 사이 입니다.)**
    * https://www.youtube.com/playlist?list=PLhr1KZpdzukcOr_6j_zmSrvYnLUtgqsZz
        * Fully-Managed Notebook Instanaces with Amazon SageMaker - a Deep Dive
        * Built-in Machine Learning Algorithms with Amazon SageMaker - a Deep Dive


* SageMaker 데이터 전처리, 모델 빌딩, 훈련 및 배포 (원제: SageMaker Pipelines 을 Step by Step 으로 배우기 )
    - https://www.youtube.com/watch?v=7IL_0-OjZWk



* <Level 100-200> SageMaker 최초 실습
    *  한글 워크샵 사이트(https://www.sagemaker-workshop-kr.com/kr)에서 다음 두 모듈을 진행합니다.(빌트인 알고리즘 활용)
        * `o` 모듈1 SageMaker > S3 bucket과 노트북 생성하기 - https://www.sagemaker-workshop-kr.com/kr/sagemaker/_module_1.html
        * `o` 모듈2 Linear Learner MNIST - https://www.sagemaker-workshop-kr.com/kr/sagemaker/_module_2.html
    * 기본 Tabular 데이터를 사용: Tabular 데이타를 모델 빌딩, 훈련, 배포, 추론을 해볼 수 있는 예제 입니다.
    * 아래에서 아래 세 개의 노트북만을 진행 함.
        * Warmingup1 - 오픈소스 XGBoost getting-started 
        * Warmingup2 - Warmingup1 예제를 Sagemaker에서 동작하도록 수정하기 
        * 다이렉트 마케팅 (SageMaker 내장 알고리즘 XGBoost 사용)
            * https://github.com/aws-samples/aws-ai-ml-workshop-kr/tree/master/sagemaker/xgboost


* 아래는 **공식 AWS 머신 러닝의 교육** 에 사용되는 많은 유용한 링크가 있는 Git 입니다. 꼭 한 번 눌러 봐주세요.
    - [The Machine Learning pipeline on AWS](https://github.com/serithemage/AWS_AI_Study/tree/master/ML_Pipeline)
* SageMaker JumpStart 입니다. 미리 만들어진 솔루션, 알고리즘 등이 있어서 샘플코드를 가지고 사직하기에 좋습니다. 개발자 가이드 문서이니 한번 보시는 것을 권장 드립니다.
    - [SageMaker JumpStart](https://docs.aws.amazon.com/ko_kr/sagemaker/latest/dg/studio-jumpstart.html)



## 3. AWS AI/ML 리소스 허브, 특집 이벤트 및 AWS ML 전문가 링크
---
### 3.1. AWS AI/ML 리소스 허브
- [AI/ML 리소스 허브](https://kr-resources.awscloud.com/aws-ai-and-machinelearning?sc_channel=el&sc_campaign=apac_field_t1_kr-aws-innovate-aiml_20220224_7014z000000rmip&sc_publisher=other&sc_country=kr&sc_geo=apj&sc_category=multi&sc_outcome=field&trkcampaign=innovate-ml&trk=el_spkrqr_kr_innovateaiml_22q1)


### 3.2. <Level 200-300> 2022 Seoul Summit AI/ML Session
- [실전! 대용량 데이터를 이용한 초거대 모델 학습 환경 만들기 - 최영준 솔루션즈 아키텍트, AWS :: AWS Summit Korea 2022](https://www.youtube.com/watch?v=l1FSiRbEja4&list=PLORxAVAC5fUX7j65Uvp9xAi1hMS6M-2P1&index=35)
- [이제, 모델 서빙 패턴의 전문가가 되어보세요! - 김대근 AIML 스페셜리스트 솔루션즈 아키텍트, AWS :: AWS Summit Korea 2022](https://www.youtube.com/watch?v=cHNe_AQWWi0&list=PLORxAVAC5fUX7j65Uvp9xAi1hMS6M-2P1&index=59)
- [스마일게이트 게임 플랫폼 ‘스토브’의 결제 사기 탐지 서비스 구축 사례 - 문곤수, 장준성, AWS / 전성현, 스마일게이트 :: AWS Summit Korea 2022](https://www.youtube.com/watch?v=MdjlJxXOzPw&list=PLORxAVAC5fUX7j65Uvp9xAi1hMS6M-2P1&index=36)

### 3.3. <Level 100-300> 2022 AWS AIML 스페셜 웹비나
- 12+ 세션 (SageMaker, Personalize) --> [전체 세션 목록](https://www.youtube.com/playlist?list=PLORxAVAC5fUULZBkbSE--PSY6bywP7gyr)
    - 세이지 메이커 시리즈 첫 번째
        - [Amazon SageMaker 모델 학습 방법 소개 - 최영준, AI/ML 엑스퍼트 솔루션즈 아키텍트, AWS :: AWS AIML 스페셜 웨비나](https://www.youtube.com/watch?v=oQ7glJfD-BQ&list=PLORxAVAC5fUULZBkbSE--PSY6bywP7gyr&index=1)
    - 퍼스널라이즈 시리즈 첫 번째
        - [Amazon Personalize 소개 (+ 실습 구성) - 김영진, 솔루션즈 아키텍트, AWS :: AWS AIML 스페셜 웨비나](https://www.youtube.com/watch?v=Och2ml4mB0s&list=PLORxAVAC5fUULZBkbSE--PSY6bywP7gyr&index=8)

### 3.4. <Level 200-300> 2022 AI/ML Innovate
- [전체 채널](https://www.youtube.com/playlist?list=PLORxAVAC5fUVqyzPFUXdNnD8k1KYRDbwI)
- SageMaker 기술 세션
    - [ML 데이터 준비 및 ML Workflow 프로토타이핑 배워보기 - 문곤수, AWS](https://youtu.be/ndHnRTiQcPY)
    - [Amazon SageMaker를 이용한 시계열 예측 모델 개발 및 MLOps 구성 방법 알아보기 - 강민재, AWS](https://youtu.be/_ia9AA3xYcc)
    - [신속한 가치 전달을 위한 전사 ML 플랫폼 구축하기 - 이유동, AWS](https://youtu.be/5h-ebraYu5s)
    - [모두를 위한 클라우드 네이티브 한국어 자연어 처리 모델 훈련 및 활용법 - 김대근, AWS](https://youtu.be/0Fl2gczVFwc)

### 3.5. <Level 200-300> 2021 AI/ML Innovate
- Amazon SageMaker SDK 2.x 사용법 (5가지 핵심 오브젝트) – 강성문:: AWS Innovate 2021
    - https://www.youtube.com/watch?v=n2Ky1nZXyWo
- Amazon SageMaker 기반 사전 훈련된 딥러닝 모델 손쉽게 배포하기 – 김대근:: AWS Innovate 2021
    - https://www.youtube.com/watch?v=ZdOcrLKow3I
- Amazon SageMaker를 통한 딥러닝 분산 학습 및 디버거 프로파일링 활용하기 – 최영준:: AWS Innovate 2021
    - https://www.youtube.com/watch?v=lsTtoACAPj4
- Amazon SageMaker와 CDK를 활용한 딥러닝 모델 서비스 현대화 기법 – 최권열:: AWS Innovate 2021
    - https://www.youtube.com/watch?v=kn2DBjZW5W8

### 3.6. <Level 100-200> 2020 Re-Invent AI/ML 서비스 소개
- Deep Dive - 신규 AI 서비스 | AWS Hero Talk - 딥레이서 살펴보기 :: AWS re:Invent Daily Recap (12월 3일)
    * https://www.youtube.com/watch?v=CtRMgSDbwA4&list=RDCMUCM9urpxJaoPf-j1cV9pGszg&index=7


- AIML 기조연설 요약 및 Deep Dive - SageMaker 살펴보기 :: AWS re:Invent Daily Recap (12월 9일)
    * https://www.youtube.com/watch?v=8fhQHpg9r9Y&list=RDCMUCM9urpxJaoPf-j1cV9pGszg&index=20


### 3.7. AWS ML 전문가 코드 리파지토리
- [AWS Korea 공식 코드 리파지토리](https://github.com/aws-samples/aws-ai-ml-workshop-kr)
- [Daekeun Kim](https://github.com/daekeun-ml)
- [Leon Kang](https://github.com/mullue)
- [Napkin-DL](https://github.com/Napkin-DL)
- [lunarian60](https://github.com/lunarian60)
- [Youngjin Kim](https://github.com/comeddy)

## 4. SageMaker 기본
---

### **목표: 세이지 메이커의 유스 케이스별 사용 알기**

* 공식 예제 사이트: Amazon SageMaker Example Notebooks (영어)
    * **공식 SageMaker 의 공식 예제 설명 문서 입니다. 모든 공식 샘플이 있기에 필요할때 마다 필요한 것을 찾아서 보시면 되겠습니다.**
    * 단계 별, 주제 별로 모든 공식 예제가 정리 되어 있습니다. 1. Getting Started, 2. SageMaker Studio, 3. AutoPilot 4.Ingest Data, 5. Label Data, 6.Prep Data, 7.Feature Store 8.Training 9.Inference 10.Frameworks 11. Workflows 12.Advanced Examples 13. Community Examples 의 대 카테고리 밑에 샘플 예제의 설명 및 코드가 있습니다.
    * https://sagemaker-examples.readthedocs.io/en/latest/index.html
        * 공식 Git: https://github.com/aws/amazon-sagemaker-examples
* 공식 영문 ML 블로그: 적용 사례, 다른 aws서비스와의 통합관련 예제나 기술 팁등 다양한 주제들이 다루어집니다.
    * [AWS English ML blog](https://aws.amazon.com/ko/blogs/machine-learning/)
* 공식 한글 ML 블로그: 적용 사례, 다른 aws서비스와의 통합관련 예제나 기술 팁등 다양한 주제들이 다루어집니다.
    * [AWS 한글 기술 ML blog](https://aws.amazon.com/ko/blogs/tech/category/artificial-intelligence/amazon-machine-learning/)


- Julien Simon의 (SageMaker 이멘젤리스트) 유튜브 비디오
    - https://www.youtube.com/c/juliensimonfr/featured
    

- Experiment & Debugger
    - 웹비나:  [How to Train and Tune Your Models with Amazon SageMaker - AWS Online Tech Talks](https://www.youtube.com/watch?v=Tnv6HsT1r4I)
        - 모델의 반복적인 실험 및 디버깅을 통한 예시 (Network Pruning 예시) 
    
    
* Use Case 별 예제 및 자료
    * 한글 예제 사이트
        * 데이터 분석과 머신러닝
            * 클라우드 기반 데이터 분석 및 인공 지능을 위한 비즈니스 혁신: https://www.youtube.com/watch?v=24YgdrJ9r-A
            * 수백만 사용자 대상 기계 학습 서비스를 위한 확장 비법 - https://www.youtube.com/watch?v=RYzviz-uOCU
        * 테블러 (테이블 데이터)
            * 배송 시간 예측하기: 테이블(Tabular) 데이터 및 AutoGluon, XGBoost 알고리즘을 이용 (AutoGluon 사용에 초점)
                * https://github.com/gonsoomoon-ml/predict-delivery-time
            * SageMaker로 싱글 타임시리즈 시계열 예측 워크샵: https://github.com/gonsoomoon-ml/linear-regresson-forecast
            * Inference Pipeline을 이용한 고객 이탈 예측 모델 및 평가 (Churn Prediction Model): https://github.com/gonsoomoon-ml/churn-prediction-workshop
        * 자연어 (NLP)
            -  <Level 200-300> [NLP 텍스트 분류를 위한 Hugging Face on SageMaker 워크샵](https://github.com/gonsoomoon-ml/NLP-HuggingFace-On-SageMaker)
            - [Level 200-300] [Amazon SageMaker 기반 한국어 자연어 처리 샘플](https://github.com/daekeun-ml/sm-kornlp-usecases)
            * [Level 200-300] 토픽 모델링을 사용한 온라인 상품 부정 리뷰 분석: https://github.com/gonsoomoon-ml/topic-modeling
            * <Level 100-200> 빌트인 알고리즘을 이용한 한글처리 - https://github.com/daekeun-ml/blazingtext-workshop-korean
            * BERT 이용한 한글처리 - https://github.com/daekeun-ml/kobert-workshop
        * 영상 (Vision)
            * <Level 200-300> 이미지의 피쳐 벡터 및 Elastic Search 를 통해 이미지 검색 만들기
                - [Amazon SageMaker로 딥 러닝 기반 이미지 검색 서비스 만들기 | 개념부터 구현까지 완전 정복](https://www.youtube.com/watch?v=RkL470RnNZY)
            * <Level 200-300> 자동차 번호판 인식 문제 해결에 SageMaker 적용해보기 - https://github.com/mullue/lab-custom-model-anpr
        * 기타
            * Tensorflow 활용실습 (Tensorflow 2.0 script mode와 stepfunctions사용하기) 
                *  https://github.com/mullue/sm-tf2
            * Kubernetes와 Sagemaker를 활용하여 기계학습 워크로드 관리하기:  https://www.youtube.com/watch?v=6sogVHw9jZ4
            * SageMaker와 EFS 연결하기 - https://aws.amazon.com/ko/blogs/machine-learning/speed-up-training-on-amazon-sagemaker-using-amazon-efs-or-amazon-fsx-for-lustre-file-systems/
            * Kubernetes Kubeflow와의 통합 - https://aws.amazon.com/ko/blogs/machine-learning/introducing-amazon-sagemaker-components-for-kubeflow-pipelines/
            * Elasticsearch와 연계한 이미지 검색 시스템 - https://aws.amazon.com/ko/blogs/machine-learning/building-a-visual-search-application-with-amazon-sagemaker-and-amazon-es/
            * Ground Truth를 이용한 3D 레이블링 - https://aws.amazon.com/ko/blogs/machine-learning/labeling-data-for-3d-object-tracking-and-sensor-fusion-in-amazon-sagemaker-ground-truth/
            * DLAMI를 이용한 분산학습 - https://aws.amazon.com/ko/blogs/machine-learning/multi-gpu-distributed-deep-learning-training-at-scale-on-aws-with-ubuntu18-dlami-efa-on-p3dn-instances-and-amazon-fsx-for-lustre/
        * 유스케이스별로 deploy하여 확인할 수 있는 케이스는 aws solutions ML 섹션을 참고하십시오.
            * - https://aws.amazon.com/solutions/implementations/?solutions-all.sort-by=item.additionalFields.sortDate&solutions-all.sort-order=desc&awsf.AWS-Product%20Category=tech-category%23ai-ml
    * 워크샵
        *  동일 사이트의 reference 페이지 (https://www.sagemaker-workshop-kr.com/kr/references.html)



## 5. 유용한 자료 (백서 등)
---

* ML 프로젝트 전반에 대한 이해가 필요하시면 다음 AWS ML백서들이 도움이 되실 수 있습니다.
    - AWS 딥러닝 가이드 백서 입니다.
        - [한글] AWS 기반 딥러닝 백서 (2019년 8월)
            - https://d2908q01vomqb2.cloudfront.net/7b52009b64fd0a2a49e6d8a939753077792b0554/2020/08/06/Deep_Learning_on_AWS_KO-KR.pdf
        - [영문] Deep Learning on AWS (2019년 8월)
            - https://d1.awsstatic.com/whitepapers/Deep_Learning_on_AWS.pdf?did=wp_card&trk=wp_card
    - ML Project 수행에 대한 베스트 프렉티스 가이드 입니다.
        - 림크 깨짐: https://d1.awsstatic.com/whitepapers/aws-managing-ml-projects.pdf?did=wp_card&trk=wp_card
    - AWS ML Well Architect Framework (WAF)
        * ML 의 WAF 내용 백서 입니다.
        * https://d1.awsstatic.com/whitepapers/architecture/wellarchitected-Machine-Learning-Lens.pdf
        
        
* 외부 사이트
    * [medium.com](http://medium.com/) 에서 검색해서 사용
    * 비젼 딥 러닝
        * 라온 피블 블로그
        * https://m.blog.naver.com/PostList.nhn?blogId=laonple
    * NLP 딥러닝
        * 딥 러닝을 이용한 자연어 처리 입문
        * https://wikidocs.net/book/2155


## 6. 체계적인 교육
---

- [한국어] Manufacturing Boost Program (AI/ML 섹션)
    - AI/ML Basics, AI/ML Advanced 참조
    - http://www.awsboost.io/
* Coursera Sagemaker - https://www.coursera.org/lecture/aws-machine-learning/introduction-to-amazon-sagemaker-QugTh
* Coursera computer vision - https://www.coursera.org/learn/aws-computer-vision-gluoncv
* Deep Learning Specialisation (코세라)
    * 총 5개의 코스로 구성됨: Neural Networks and Deep Learning, Improving Deep Neural Networks: Hyperparameter Tuning, Regularization and Optimization, Structuring Machine Learning Projects, Convolutional Neural Networks(CNN), Sequence Models(RNN)
    * https://www.coursera.org/specializations/deep-learning
* Udacity nanodegree 코스 - https://www.udacity.com/course/machine-learning-engineer-nanodegree--nd009t



## 7. 아마존 사이언스
---
### 7.1 Amazon Science
- Top articles in 2021
    - https://www.amazon.science/latest-news/the-top-amazon-science-articles-of-2021)
- Top blog posts in 2021
    - https://www.amazon.science/latest-news/the-top-amazon-science-blog-posts-of-2021
- Most downloaded papers in 2021
    - https://www.amazon.science/latest-news/the-top-amazon-science-articles-of-2021

### 7.2 최신 트랜드
- 2021년 기계학습 연구 트렌드
    -  https://velog.io/@aldente0630/2021년-기계-학습과-자연어-처리-연구-하이라이트

### 7.3 대학교 AWS SageMaker 커리큘럼 수업 예시

(1) 전체 과정 소개

(2) AWS 활용 준비하기, AWS Educate 가입 등

(3) 실습 환경 구축 SageMaker 소개, Jupyter Notebook 인스턴스 생성 실습

* 기초 핸즈온 수행 (위의 SageMaker 선수 지식 및 101 과정 참고)

(4) 기계학습 소개 이론
(5) 선형회귀분석 이론 및 Jupyter Notebook 코드리뷰 이론 + 실습

* Regression with Amazon SageMaker Linear Learner algorithm
    * https://github.com/aws/amazon-sagemaker-examples/blob/master/introduction_to_amazon_algorithms/linear_learner_abalone/Linear_Learner_Regression_csv_format.ipynb

(6) 트리 이론 및 Jupyter Notebook 코드리뷰 이론 + 실습

* *Gradient Boosted Trees를 이용하는 지도학습: 편향된 클래스의 이진 분류 예측문제 해결*
* https://github.com/mullue/xgboost/blob/master/1.xgboost_direct_marketing_sagemaker.ipynb

(7) 인공신경망 이론 및 Jupyter Notebook 코드리뷰 이론 + 실습

(8) k-means 이론 및 Jupyter Notebook 코드리뷰 이론 + 실습

* Analyze US census data for population segmentation using Amazon SageMaker
    * https://github.com/aws/amazon-sagemaker-examples/blob/master/introduction_to_applying_machine_learning/US-census_population_segmentation_PCA_Kmeans/sagemaker-countycensusclustering.ipynb

(9) 텍스트 데이터 분석 이론 및 Jupyter Notebook 코드리뷰 이론 + 실습

* 토픽 모델링을 사용한 온라인 상품 부정 리뷰 분석
    * https://github.com/gonsoomoon-ml/topic-modeling

(10) Amazon SageMaker 를 활용한 모델 배포 실습

* TensorFlow 2 프로젝트 워크플로우를 SageMaker에서 실행하기
    * https://github.com/mullue/sm-tf2/blob/master/tf-2-workflow.ipynb




