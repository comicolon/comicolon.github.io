---
layout : post
title : Hypothesis Test
description :
parent : data handling
has_children: false
nav_order : 5
use_math : true
mathjax : true
---

# Hypothesis Test
{: .text-center}

## 기술 통계
수집한 데이터를 요약 묘사 설명하는 통계 기법
+ boxplot
+ bagplot
+ violin plot

## 추리 통계
수집한 데이터를 바탕으로 추측 예측하는 통계 기법

## Effective Sampling

1. Simple Random Sampling
2. Systematic Sampling
3. Stratified Random Sampling
4. Cluster Sampling

## 표본 평균의 표준 오차

__결론: 표본의 수가 더욱 많아질수록, 추측은 더 정확해지고 (평균) 높은 신뢰도를 바탕으로 모집단에 대해 예측 할 수 있도록 함__

## T-test
t-test를 이용하기 위한 몇가지 조전
+ 독립성 : 두 그룹이 연결되어 있는 (paired) 쌍인지
+ 등분산성 : 두 그룹이 어느정도 유사한 수준의 분산 값을 가지는지
+ 정규성: 데이터가 정규성을 나타는지

### One Sample t-test
1개의 sample 값들의 평균이 특정값과 동일한지 비교.

#### One-side test vs Two-side test
Two side (tail / direction) test : 샘플 데이터의 평균이 "X"와 같다 / 같지 않다. 를 검정하는 내용  
One side test : 샘플 데이터의 평균이 "X"보다 크다 혹은 작다 / 크지 않다 작지 않다. 를 검정하는 내용

## Two Sample T-test

2개의 sample 값들의 평균이 서로 동일한지 비교.

p-value
{: .text-red-100 .fs-6}
> P-value 는, 주어진 가설에 대해서 "얼마나 근거가 있는지"에 대한 값을
> 0과 1사이의 값으로 scale한 지표 이며
> p-value가 낮다는 것은, 귀무가설이 틀렸을 확률이 높다.

## x2 test
+ 관찰된 빈도가 기대되는 빈도와 유의미 하게 다른지 검증
+ __범주형__ 자료로 구성된 데이터 분석에 사용
+ $ x^2 = \sum (관측값 - 기대값)^2) / 기대값$


## 자유도 (Degrees of Freedom)

자유도 = n - 1







