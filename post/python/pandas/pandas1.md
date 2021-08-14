---
layout: post
title: 판다스 기본 
date : 2021-08-14
# last_modified_date : 2021-08-06
parent: pandas
grand_parent: python
---

# 판다스 사용법
기본적인 몇가지 사용법을 알아보자

## 1. 데이터 프레임 만들기

### 1-1. 기본 만들기
```python
import pandas as pd

messenger_list = [
    ['whatsApp', 2009, 1500],
    ['line', 2011, 203],
    ['facebook', 2011, 1300]
]
column_name = ['name', 'since', 'user']

df = pd.DataFrame.(messenger_list, columns = column_name, 
    index=['a','b','c'])
```

리스트의 리스트 형태로 데이터셋을 만들고  
컬럼 네임의 리스트를 만들고   
인덱스 역시 리스트 형태로 넣어준다.

pd.DataFrame(__데이터, 컬럼, 인덱스__ 를 넣어준다)  
인덱스를 지정하지 않으면 0 부터 순서대로 들어간다<br/><br/>

---
파이썬 리스트 트릭
 ```python
 aa = list['abcdefg']
 print(aa)
 ```
 
> out : ['a', 'b', 'c', 'e', 'f', 'g']

판다스 날짜 다루기
```python
 dates = pd.date_range('20130101', periods=6)
 print(dates)
```
> out : DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04', '2013-01-05', '2013-01-06'], dtype='datetime64[ns]', freq='D')


---
<br/>




