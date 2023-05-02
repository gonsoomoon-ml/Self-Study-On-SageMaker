
# 데이터 전처리 기본 가이드 
---

**마지막 업데이트: 2023.05.02**


# 1. 한글에서 특수 문자 제거 코드
- 아래는 한글에서 특수 문자를 제거하는 코드 샘플 입니다.

```python
import re
def remove_spec_chars(s):
    '''
    특수 문자 제거.
    '''
    if pd.isnull(s):
        return s
    s = re.sub(r'\W+', ' ', s)   # 알파벳, 숫자 이외 모두 제거
    
    remove_ptns = ['\r', '\n', '>','<','{','}','[',']',']'
                   '$','/', ',','-','_','=','+','.','!','@','^','%','#','*','(',')',
                   '₩','`','&','|',':',';','<','>','?','\\','\'','"'
                  ]
    
    dic = dict(zip(remove_ptns, [' '] * len(remove_ptns)))
    regex = re.compile("|".join(map(re.escape, dic.keys())), 0)
    s = regex.sub(lambda match: dic[match.group(0)], s)
    s = re.sub('\s+',' ', s)

    return s


def pre_process_NLP(df, target_col, new_col):        
    temp = df.copy()

    temp[new_col] = temp[target_col].apply(remove_spec_chars)

    return temp

import pandas as pd

d = {'id': [1, 2], 
     'item_nm': ['[핫세일] 언제나~ 먹어도 건강에 좋은 아침 샐러드!'
                 ,'(계절 상품 입고) 집에서 4계절 편하게 ^^ 입는 통풍 바지 @@@@']}

df = pd.DataFrame(data=d)

new_df = pre_process_NLP(df, target_col='item_nm', new_col='item_nm_new')
new_df

	id	item_nm	                                         item_nm_new
0	1	[핫세일] 언제나~ 먹어도 건강에 좋은 아침 샐러드!	         핫세일 언제나 먹어도 건강에 좋은 아침 샐러드
1	2	(계절 상품 입고) 집에서 4계절 편하게 ^^ 입는 통풍 바지 @@@@	 계절 상품 입고 집에서 4계절 편하게 입는 통풍 바지
```