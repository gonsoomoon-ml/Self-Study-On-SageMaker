# 유용한 명령어

**마지막 업데이트: 2021.09.27**
**작성자: 문곤수**

---

### \# 도커 관련 명령어

#### No space left (용량 부족시)

- 모든 컨테이너 모두 삭제
    - `docker container prune -f` 


- 모든 이미지 모두 삭제
    - `docker image prune -f --all`


- 추가적인 용량 삭제가 필요하면 아래를 실행 하세요
    - `rm -rf /tmp/tmp*`
    
    
- 참조: 
    - 도커로 사용으로 인한 시스템 용량 확보
        - [Docker의 prune 사용법](https://www.lainyzine.com/ko/article/docker-prune-usage-remove-unused-docker-objects/)
    




### \# 파이썬에서 상위 폴더의 파일을 로딩 하는 방법

- 아래와 같이 폴더 구조가 있다가 가정하고, 1_data_preparation.ipynb 노트북에서 아래와 같은 import를 사용하여 lookout_equipment_utils.py 안에 있는 함수를 로딩 함.

``` 
|-dataset
 |-utils
 | |-lookout_equipment_utils.py
 | |-aws_matplotlib_light.py
 |-notebooks
 | |-1_data_preparation.ipynb
 

sys.path.append('../utils')
import lookout_equipment_utils as lookout 
```

### \# 캐글 데이터 셋 다운로드 방법
- [Kaggle Dataset 다운로드 방법](https://github.com/mullue/amazon-sagemaker-architecting-for-ml/blob/master/Starter-Code-kr/How_to_downlaod_kaggle_data/0.download_kaggle_dataset.ipynb)

### \# SageMaker Notebook Instance 에서 컨솔로 커널 접근 후 패키지 설치

```
conda env list # 커널 리스트
source activate mxnet_p36 # mxnet_p36 커널로 이동
pip install -r requirements.txt # requirements.txt 안에 있는 파이썬 패키지 설치

```
- 관련 링크: [Python 패키지를 Amazon SageMaker 노트북 인스턴스의 Conda 환경에 설치하려면 어떻게 해야 하나요?](https://aws.amazon.com/ko/premiumsupport/knowledge-center/sagemaker-python-package-conda/)

### \# SageMaker Studio 의 이미지 터미널에서 net-tools 설치

```
apt update
apt install net-tools
netstat
apt install telnet
telnet
```




### \# Linux 에서 파일 폴더 및 파일 리스트 출력

```
find . | sed -e "s/[^-][^\/]*\// |/g" -e "s/|\([^ ]\)/|-\1/"

예시 결과:
 |-training_tensorflow
 | |-tensorflow_train.py
 | |-requirements.txt
 |-1.1.download_data.ipynb
 |-1.2.structuring_data.ipynb 
 |-img
 | |-cifar-10.png
 | |-coco.png
```
