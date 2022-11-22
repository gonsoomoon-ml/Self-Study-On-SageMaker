# 유용한 명령어: Git Command

**마지막 업데이트: 2022.11.22**


---

# 1. Git Pull 에러시
---

## 1.1. 아래왁 같이 git pull 에러시에 하나의 "간단한" 방법으로서 원격 repo 와 로컬 repo 간의 merge 를 통해서 해결 한다. 
```bash
sh-4.2$ git pull
hint: You have divergent branches and need to specify how to reconcile them.
hint: You can do so by running one of the following commands sometime before
hint: your next pull:
hint: 
hint:   git config pull.rebase false  # merge
hint:   git config pull.rebase true   # rebase
hint:   git config pull.ff only       # fast-forward only
hint: 
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation.

fatal: Need to specify how to reconcile divergent branches.
sh-4.2$ git config pull.rebase false
sh-4.2$ pwd
/home/ec2-user/SageMaker/Neural-Collaborative-Filtering-On-SageMaker
sh-4.2$ git pull
Merge made by the 'ort' strategy.
 3_MLOps/3_hello-codepipeline/CloudFormation/MLOPS-IAM.yaml | 6 +++---
 1 file changed, 3 insertions(+), 3 deletions(-)
sh-4.2$ git pull
Already up to date.
```
- 하지만 "안전한" 다른 방법으로 로컬에 브랜치를 생성하여 머지 하는 방법도 있습니다. 아래 링크를 참조 하세요.
    - [[Git] git pull error: 브랜치 merge할 때 발생하는 에러](https://velog.io/@s_yeah/Git-git-pull-error-%EB%B8%8C%EB%9E%9C%EC%B9%98-merge%ED%95%A0-%EB%95%8C-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94-%EC%97%90%EB%9F%AC)
    
## 1.2. 로컬 repo 에서 작업시에 git pull 시 에러
```
Updating a0a20bc..2e73e77
error: Your local changes to the following files would be overwritten by merge:
        3_MLOps/1_sm_training_pipeline/1.1.Prepare-Dataset.ipynb
        3_MLOps/1_sm_training_pipeline/3.1.NCF-Training-Pipeline.ipynb
Please commit your changes or stash them before you merge.
Aborting
sh-4.2$ git stash
Saved working directory and index state WIP on main: a0a20bc edit requirement.txt
sh-4.2$ git pull
Updating a0a20bc..2e73e77
Fast-forward
 3_MLOps/1_sm_training_pipeline/1.1.Prepare-Dataset.ipynb       | 32 +++++++++++++++++++++-----
 3_MLOps/1_sm_training_pipeline/3.1.NCF-Training-Pipeline.ipynb | 96 +++++++++++++++-------------------------------------------------------------
 2 files changed, 44 insertions(+), 84 deletions(-)
```
- 참고 사항
    - [[Git (6)] git pull 에러 해결방법 (Your local changes to the following files would be overwritten by merge )](https://goddaehee.tistory.com/253)