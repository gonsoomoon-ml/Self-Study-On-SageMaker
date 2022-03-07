# 에러: 1.2 SageMaker Classic Notebook 에서 Local Mode 사용시 Shared Memory (shm) 제약 사항 (64MB)
## 1. 에러 현상
- 관련 에러 메세지
    - a3ku9xqv1y-algo-1-1kcnw | [1,2]:RuntimeError: DataLoader worker (pid 1219) is killed by signal: Bus error. It is possible that dataloader's workers are out of shared memory. Please try to raise your shared memory limit.


- SageMaker Classic Notebook 에서 Local Mode docker 를 실행시에  Shared Memory 가 부족하여 생기는 현상 입니다. 예를 들어서 Pytorch 의 data loader 를 사용시에 메모리가 부족해서 에러가 발생할 수 있습니다.
    

## 2. 워크라운드
- 설정 파일: local_mode_setup.tar
    - 이 깃 리파지토리를 다운로드
        - 위치: Self-Study-On-SageMaker/workaround/local_mode_setup.tar
    - 이 파일을 세이지 메이커 노트북 인스턴스에 업로드
    - 터미널을 생성하고 설정 파일을 압출 해제 하세요.
        - tar -xzf local_mode_setup.tar
    - 그리고  터미널에서 아래와 같이 명령 실행 합니다.


```
sh-4.2$ ls local
daemon.json  local_mode_setup.sh
sh-4.2$ cat local/daemon.json 

{
        "default-runtime": "nvidia",
    "runtimes": {
        "nvidia": {
            "path": "/usr/bin/nvidia-container-runtime",
            "runtimeArgs": []
        }
    },
    "data-root": "/home/ec2-user/SageMaker/.container/docker",
    "default-shm-size": "5G" 
}
sh-4.2$ bash local/local_mode_setup.sh 
nvidia-docker2 already installed. We are good to go!
sudo: systemctl: command not found
Stopping docker:                                           [  OK  ]
Starting docker:        .                                  [  OK  ]
SageMaker instance route table setup is ok. We are good to go.
SageMaker instance routing for Docker is ok. We are good to go!
sh-4.2$ 
```


- 위와 같이 명령을 실행 한 후에 data-root 의 위치 및 default-shm-size 가 5G 가 됩니다.
- 로컬모드를 실행하는 노트북의 커널을 재시작하시고, 로컬모드로 실행 해보세요.