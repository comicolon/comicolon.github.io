---
layout : post
title : eda
description : 데이터 다루기
parent : data handling
has_children: false
nav_order : 1
---

# EDA (Exploratory Data Analysis)

EDA 란?
데이터 분석의 __초기 단계__
+ 패턴의 발견
+ 데이터의 특이성 발견
+ 통계와 그래픽으로 가설 검정

그래픽과 논그래픽의 방법이 있다.

## pandas에서의 기초 EDA

### Missing data
+ isna
+ isnull
+ notna
+ notnull
+ dropna
+ fillna

### Data Frame
- index
- columns
- dtypes
- info
- select_dtypes
- loc
- iloc
- insert
- head
- tail
- apply
- aggregate
- drop
- rename
- replace
- nsmallest
- nlargest
- sort_values
- sort_index
- value_counts
- describe
- shape

### Vis
- plot
- plot.area
- plot.bar
- plot.barh
- plot.box
- plot.density
- plot.hexbin
- plot.hist
- plot.kde
- plot.line
- plot.pie
- plot.scatter