# Development Environment : Self-Study-On-SageMaker

**마지막 업데이트: 2023.07.11**


---

# 1. Amazon CodeWhisperer 사용하기
- 코딩 생산성을 엄청 올릴 수 있습니다. 아래 링크 통해서 자세한 내역 확인 하세요.
    - [README-CodeWhisperer.md](README-CodeWhisperer.md)

# 2. 클라우드가 아닌 로컬 머신에서 훈련 코드 환경 만들기 
- [로컬 머신에서 Visual Studio Code 를 사용하여 SageMaker 훈련 코드 작성 하기](README-Local-VS-Code.md)

# 3. SageMaker Notebook에서 로컬 모드 사용 방법
- 로컬모드의 사용을 위해서는 docker-compose 가 필요한데요, SageMaker Python SDK 의 호환을 위해서 기본 설치된 docker-compose 가 설치가 안된다고 합니다. (2023. 07. 11). 아래와 같이 추가적으로 설치하시면 됩니다.
    - https://github.com/aws/sagemaker-python-sdk/blob/master/doc/overview.rst#local-mode
```
curl -L "https://github.com/docker/compose/releases/download/v2.7.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

# 4. SageMaker Studio 론칭 방법
- SageMaker Console 에 접근해서 론칭
- API 를 통하여 presigned-domain-url 를 제공 받은 후에 론칭
    - [PresignedUR 사용하기](README-PresignedURL.md)
    
    
# 5. 세이지 메이커의 개발 환경
- JupyerLab3 출시 : 코딩 생산성 좋아졌습니다. ^^  --> [Amazon SageMaker Studio and SageMaker Notebook Instance now come with JupyterLab 3 notebooks to boost developer productivity](https://aws.amazon.com/blogs/machine-learning/amazon-sagemaker-studio-and-sagemaker-notebook-instance-now-come-with-jupyterlab-3-notebooks-to-boost-developer-productivity/)
    