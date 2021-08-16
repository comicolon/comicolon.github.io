---
layout : post
title : High dimensional data
description :
parent : data handling
has_children: false
nav_order : 8
use_math : true
date : 21-08-16
# last_modified_date : 2021-08-06
---

# High dimensional data (고차원 데이터)
{: .text-center}

## Vector transformation

## 고유벡터 (Eigenvector)

 transformation에 영향을 받지 않는 회전축, (혹은 벡터)을 공간의 고유벡터 (Eigenvector)라고 부릅니다.

## 고유값 (Eigenvalue)

고유 벡터의 길이가 변하는 배수를 선형 변환의 그 고유 벡터에 대응하는 고유값 이라고 한다. 

# 고차원의 문제 (The Curse of Dimensionality)
{: .text-center}

## PCA Process
> 다차원의 데이터를 시각화 하기 위해서 2차원으로 (scatter) 축소하자
> 그런데 제일 정보 손실이 적은 2차원을 고르자

### PCA 특징
+ 데이터에 대해 독립적인 축을 찾는데 사용 할 수 있음
+ 데이터의 분포가 정규성을 띄지 않는 경우 적용이 어려움
  + 이경우 커널 PCA를 사용가능
+ 분류/예측 문제에 대해서 데이터의 라벨을 고려하지 않기 때문에 효과적 분리가 어려움
  + 이 경우는 PLS 사용가능