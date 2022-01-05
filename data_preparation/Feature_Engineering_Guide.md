
# Feature Engineeing 기본 가이드 
---

**마지막 업데이트: 2022.01.04**


## 1. Target Analysis 
---
머신 러닝 문제의 종류가 "Regression(회귀)" 일 경우에 레이블인 Target 의 값 분포가 Heavy Tailed Target (레이블의 값의 분포가 긴 꼬리를 가지고 있음. 예를 들어서 직장인의 연봉 액수가 Target 이면 대부분의 직장인의 연봉 분포는 앞에 분포가 되고, 임원들의 연봉은 오른쪽 꼬리에 위치가 됨) 일 경우에,긴 꼬리를 아웃라이어라 보고 제거 하거나, 따로 아웃라이어만 분리하여 모델링 하는 것을 권장.

참조
- SageMaker AutoPilot : Target Analysis
    - https://docs.aws.amazon.com/sagemaker/latest/dg/autopilot-data-exploration-report.html#autopilot-data-exploration-report-target-analysis
