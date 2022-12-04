# 유용한 명령어: Docker Command

**마지막 업데이트: 2022.12.04**


---

# 1. 도커 컨테이너 조회 및 시작
- -a 옵션을 사용하면 현재 중지되어 있는 컨테이너까지 함께 출력됩니다.
```bash
docker ps -a
```
- -s 옵션을 사용하면 각 컨테이너의 디스크 사용량까지 볼 수 있습니다.
```bash
docker ps -s
```
- 컨테이너 시작 
    - 아래 명령어를 실행하기 전에 `docker image ls` 를 통해서 imaage id 를 획득한 후에 시작하시면 됩니다.
```bash
docker start b1bae952f7a6
```

# 2. 도커 실행
docker run 커맨드의 기본 포멧은 다음과 같습니다. 여기서 이미지 식별자는 필수이며 이미지 ID나 리파지토리(repository):태그(tag)를 사용할 수 있습니다.
$ docker run (<옵션>) <이미지 식별자> (<명령어>) (<인자>)
```bash
$ docker run (<옵션>) <이미지 식별자> (<명령어>) (<인자>)
```
## 2.1. -v 옵션
-v 옵션은 호스트와 컨테이너 간의 볼륨(volumn) 설정을 위해서 사용되는데요. 호스트(host) 컴퓨터의 파일 시스템의 특정 경로를 컨테이너의 파일 시스템의 특정 경로로 마운트(mount)를 해줍니다.

- 아래 커맨드는 호스트 컴퓨터의 현재 디렉터리를 컨테이너의 /etc 경로로 마운트한 후, 그 안에 있는 test.txt 파일의 내용을 출력하고 있습니다.
```bash
docker run -v `pwd`:/etc python:3.8-alpine cat /etc/test.txt
```
- 아래 커맨드는 호스트 컴퓨터의 현재 디렉터리 기준으로 workspace 폴더를 컨테이너의 workspace 경로로 마운트한 후, generate_model_pytorch.sh 를 실행하고 있습니다.

```bash
docker run --gpus=all --rm -it \
            -v `pwd`/workspace:/workspace nvcr.io/nvidia/pytorch:22.07-py3 \
            /bin/bash generate_model_pytorch.sh
```

## 2.2. 다커 인터렉트 모드 (다커 안으로 진입)
```bash
docker exec -it \<Container ID\> /bin/bash 
```
- 실행중인 도커에 명령어 실행
    - b1bae952f7a6 이미지 아이디로 본인 것으로 교체 해야 합니다.
```bash
docker exec b1bae952f7a6 ls
```

### 참조: 아래 웹페이지를 보시면 상세한 내용이 있습니다.
- [docker run 커맨드 사용법](https://www.daleseo.com/docker-run/)


# 3. 도커 중지 및 삭제
- 도커를 중지할 경우에 사용 합니다.
```bash
docker stop amazing_chatelet
```
- -f 옵션을 사용하면 해당 컨테이너를 먼저 정지시킨 다음에 제거해줍니다.
```bash
docker rm -f d2f83048485e
```
- 실행 중인 컨테이너는 건들지 않고 중지되어 있는 모든 컨테이너를 제거하고 싶다면 다음과 같이 하면 됩니다.
```bash
$ docker rm $(docker ps -a -q)
```

# 4. 도커 관리
---
## 4.1. No space left (용량 부족시)
- 모든 컨테이너 모두 삭제
```bash
docker container prune -f
```
- 모든 이미지 모두 삭제
```bash
docker image prune -f --all
```
- 추가적인 용량 삭제가 필요하면 아래를 실행 하세요
```bash
rm -rf /tmp/tmp*
```
    
# 참조: 
- 도커로 사용으로 인한 시스템 용량 확보
    - [Docker의 prune 사용법](https://www.lainyzine.com/ko/article/docker-prune-usage-remove-unused-docker-objects/)
