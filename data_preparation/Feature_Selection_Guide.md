
# Tablur Data (CSV 데이터) 피쳐 선택 기본 가이드 
---

**마지막 업데이트: 2022.01.04**

## 1. Cardinality 확인
---
* 상식적으로 데이터 컬림이 모델의 레이블(예: 프로드) 에 영향을 주는지를 생각해야 합니다. 
    * user_id, 주민번호, 이메일 주소 같은 컬럼은 특정 사용자에게만 적용이 되기에 모델의 예측을 하는데에 도움을 주지 않습니다. 예를 들어서 honggildong@naver.com 을 넣고 레이블이 1 로 정의 되어 있고, 모델 학습을 하면, 이 이메일로 예측(추론)을 하면 모두 1로 답을 주게 됩니다. 만약에 이 이메일 주소를  바꾸어서 다른 것을 사용하게 되면 그 이메일 주소는 프로드 검출이 안됩니다. 
    * 이메일 주소에서 honggildong@naver.com 이메일 도메인을 피쳐로 사용하는 것은 의미가 있습니다. (에: naver.com, hotmail.com (http://hotmail.com/) 등). 프로드 사용자의 경우에는 1회용 이메일 주소를 발급해주는 곳이 있습니다. 이런 도메인 정보는 프로드 사용자가 자주 이용하므로 의미가 있습니다.

    
* 특정 ID (예: item_id, vendor_id, advertisement_id)
    * 이런 특정 상품, 서비스를 대표하는 것들은 모델 피쳐로 넣는 것을 지양하는 것이 좋습니다.
    * 오히려 특정 ID 를 통한 Aggregation Values (예: 특정 Item_id 가 평균 1시간에 팔리는 갯수) 로 만들어서 피쳐를 생성 하는 방법을 권장 합니다.


* Cardinality 극히 낮은 값을 봐야 합니다. 
    * 컬럼의 값이 모두 한개의 값이면, 의미가 없습니다. 이러한 것은 제거 해야 합니다. (예: Country 가 모두 한국 인 경우)


## 2. 날짜 및 숫자 관련 피쳐
---
* 날짜 값
    * 예를 들어서 날짜 변수가 createdat 가 있고 값이 이렇게 2021-10-12 13:20:20 있으면 이 또한 통째로 스트링으로 넣으면 의미가 없습니다. 이 날짜에서 요일, 시간대 (새벽, 저녁 등), 계절, 월, 1년 중의 몇 번째 주 같은 정보를 추출해서 피쳐로 넣는 것은 좋습니다.
    
    
* 숫자 값 (예: Price)
    * 처음 모델을 생성시에는 일단 숫자 값 자체로 피쳐로 사용 합니다. 이후에 숫자 값을 구간을 나누어 넣는 것의 시도를 권장 드립니다. 예를 들어서 상품의 가격을 바로 모델에 넣는 것 보다는 구간을 나누어서 넣는 것이 더 좋은 모델 성능을 제공할 수 있습니다. 예를 들어서 0-10000원, 10,000원 - 100,000원, 100,000원 - 1,000,000 만원 의 구간을 나누어서 “1_range”, “2_range”, “3_range” 이런 식으로 구간을 넣는 것이 좋습니다.
    * 연령도 비슷합니다. 하나의 연령의 숫자 보다는 연령대로 구간을 나누어서 (예: 20대, 30대) 피쳐로 넣는 것이 좋습니다.


## 3. 중복 피쳐 제거
---
* 예를 들어서 데이터 컬럼에 “신장-Cm”, “신장-Inch” 가 있다고 하면, 두개는 단위만 다를 뿐 같은 속성을 가지고 있습니다. 그래서 1개는 제거 합니다. 보통 변수들의 Correation Matrix“ 를 만들어서 유사도가 일정 수치 이상(예: 0.9, -0.9) 이면 확인하고 제거를 합니다. 양의 방향, 음의 방향으로 1과 -1에 가까운 컬럼을 제거 합니다.
* 기타
    * 숫자형의 값이 스트링으로 되어 있는 것 수정. 데이터 타입을 보고 숫자인데 string 으로 되어 있으면, 꼭 수정을 해야 합니다.


## A. 기타 
---
    
###  IP Address (예: xxx.xxx.xxx.xxx)
    * IP Address 자체만으로는 fraud detector 모델 성능에 큰 영향을 줄 수 없습니다. 
    * IP Address 에서 추출할 수 있는 정보들을 토대로 범주형 데이터를 만들어 모델에 영향을 줄 수 있습니다. 다음과 같은 정보들을 추출할 수 있습니다. Python 을 사용할 경우 IP2Locaion 같은 라이브러리를 사용할 수 있습니다.
         * Coutry
         * City
         * Region
         * ISP 
         * 기타 등등
     * 상위와 같은 정보들을 추출후 따로 컬럼을 생성해 모델에 영향을 줄 수 있는 범주형 데이터를 생성한 후 one hot encoding 등의 인코딩을 통해 모델에서 사용할 수 있습니다.
     
### 자연어 (내용이 방대하지만 여기서는 간단히만 언급 합니다.)     
* 이름 (예: Advertise Name), 자연어
    * 광고 이름 (예: 수험생을 위한 포도즙 세트)을 가공 없이 통때로 스트링으로 넣게 되면 (예: “수험생을 위한 포도즙 세트”) 이 또한 의미가 없습니다. 만약에 광고 이름의 단어가 의미가 있다고 하면, 자연어 처리 파싱을 해서, “수험생”, “포도즙”, “세트” 이런 단어를 다른 인코딩(에: TF-IDF) 을 통하여 피쳐로 넣어야 합니다. 이런식으로 따로 하지 않고 스트링 전체를 입력하는 것은 의미가 없습니다.
    * 검색 키워드
        * 예를 들어서 검색의 키워드를 피쳐로 사용하고 싶다고 하면, 이또한  바로 스트링을 모델 학습에 사용하지 않고, 인코딩 (예: TF-IDF, Word2Vec ) 을 통하여 피쳐를 생성하여 사용합니다.
    
    
## B. 참고
---
- [강력 추천] 50 Advanced Tips: Data Science for tabular data
    - https://www.kaggle.com/vbmokin/50-advanced-tips-data-science-for-tabular-data
- [강력 추천] Best Practices for ML Engineering
    - https://developers.google.com/machine-learning/guides/rules-of-ml
- Exploratory data analysis, feature selection for better ML models
    - https://cloud.google.com/blog/products/ai-machine-learning/building-ml-models-with-eda-feature-selection
- Practical advice for analysis of large, complex data sets 
    - https://www.unofficialgoogledatascience.com/2016/10/practical-advice-for-analysis-of-large.html

