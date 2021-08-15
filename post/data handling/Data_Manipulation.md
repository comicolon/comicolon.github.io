---
layout : post
title : Data Manipulation
description :
parent : data handling
has_children: false
nav_order : 3
---

# Data Manipulation
{: .text-center}

## Concat

데이터 프레임 둘을 합치는 것

pd.concat([df1,df2], axis=)
{: .text-blue-200}

df1 과 df2를 합하고 axis의 숫자에 따라서  
0 이면 행을 기준으로 아래위로 붙고  
1 이면 열을 기준으로 좌우로 붙는다.

## Merge

공통된 부분을 기반으로 합치는 것

df.merge(붙일내용, how='방법', on='기준')
{: .text-blue-200}

붙일 내용은 붙여질 데이터  
how는 방법
+ inner 중복된 데이터의 행만 합치기
+ outer 중복과 상관없이 모두 합치기
+ left 기준이 원본 데이터
+ right 기준이 붙여질 데이터
  
on 에는 기준이 되는 feature 를 넣어준다.

## isin

## groupby

## tidy data

Jeff Leek가 쓴 책 The Elements of Data Analytic Style에서 정의
1. 각 변수는 개별의 열(column)으로 존재한다.
2. 각 변수는 개별의 열(column)으로 존재한다.
3. 각 표는 단 하나의 관측기준에 의해서 조직된 데이터를 저장한다.
4. 만약 여러개의 표가 존재한다면, 적어도 하나이상의 열(column)이 공유되어야 한다.

df_tidy = df.melt(id_vars='기준', value_vars= ['feature1','feature2'])
{: .text-blue-200}

### tidy -> wide

df_wide = df_tidy.pivot_table(index = 'row', columns = 'column', values = 'value')
{: .text-blue-200}

+ index: unique identifier
+ columns: "wide" 데이터에서 column별로 다르게 하고자 하는 값.
+ values: 결과값이 들어가는 곳 (wide 데이터프레임의 내용에 들어갈 값)

