---
layout: post
title: 판다스 기본 
date : 2021-08-14
# last_modified_date : 2021-08-06
parent: pandas
grand_parent: python
---

# 판다스 사용법 
{: .text-center}
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

## 2. 데이터 프레임 접근

<brt/>
데이터 프레임으로 접근에는 크게 두가지 방법이 있다.  

__1. 명시적인 바로 접근__  
__2. loc를 이용한 접근__  
__3. iloc를 이용한 접근__


### 2-1 명시적인 접근
<br/>
다음의 두 명령들은 __모두 같은 열__ 을 출력한다.

```python
print(df.since)
print(df['since'])
```
>|a   | 2009| 
>|b   | 2011|
>|c   | 2011|

<br/>

__행__ 접근  
명시적으로 열을 지정해 줄때는 항상 범위로 접근한다.
```python
print(print(df['a':"a"]))
```
>|       |name  |since  |user|
>|a  |whatsApp   |2009  |1500|

<br/>

### 2-2 loc를 이용한 접근
<br/>

__df.loc['row','column']__  
{:.text-blue-200}

loc를 이요한 접근에는 []안에 row명을 쓰고 column명을 지정해 주면 된다.
:를 지정하면 모든 열이나 행을 지정해준다.
범위로 row나 column을 지정해 주어도 된다.

<br/>

### 2-3 iloc를 이용한 접근
<br/>

__df.iloc[0,0]__
{: .text-blue-200}

iloc 역시 loc와 순서는 같다 하지만 숫자로 인덱싱을 한다.
1, 2, 3 식으로 하나씩 넣얻줘도 된고
[1,2]식으로 리스트로 범위 지정이 가능하다

<br/>


