---
layout : post
title : Linear Regression
description :
parent : Machine Learning
has_children: false
nav_order : 1
use_math : true
date : 21-08-21
# last_modified_date : 2021-08-06
---

# Linear Regression (선형 회귀)
{: .text-center}

## 단순 선형 회귀
한개의 스칼라 독립 변수 x와 한개의 스칼라 의존 변수 y의 관계

## 다중 선형 회귀
단순 선형 회귀에서 독립 변수를 여러개로 확장한것.  
선형회귀라 함은 보통 다중 선형 회귀

## 다변량 선형 회귀
응답 변수 y가 벡터인 경우  
일반 선형 회귀라 부름

<br/>

## 기준모델 (Baseline Model)
예측 모델을 구체적으로 만들기 전에 가장 간단하면서도 직관적이면서 최소한의 성능을 나타내는 기준이 되는 모델  
평균값을 주로 쓴다.

## 예측 모델 (Predictive Model)
scatterplot에 가장 잘 맞는(best fit) 직선을 그려주면 그것이 회귀 예측모델  
**회귀선**은 잔차 제곱들의 합인 RSS((residual sum of squares)를 최소화 하는 직선  
RSS의 값이 회귀 모델의 비용함수가 된다. 

> 잔차제곱의 합을 최소화 하는 방법을 최소제곱 회귀 혹은 Ordinary least squares(OLS)라고 부름


+ 종속변수는 반응(Response)변수, 레이블(Label), 타겟(Target)등으로 불립니다.
+ 독립변수는 예측(Predictor)변수, 설명(Explanatory), 특성(feature) 등으로 불립니다.

## 선형회귀모델의 계수(Coefficients)
독립변수의 최소단위가 변할 때 마다 변하는 종속 변수의 수치

## 회귀 모델을 평가하는 평가지표

+ MSE (Mean Squared Error) = $\frac{1}{n}\sum_{i=1}^{n}(y_{i} - \hat{y_{i}})^{2}$
+ MAE (Mean absolute error) = $\frac{1}{n}\sum_{i=1}^{n}\left \vert y_{i} - \hat{y_{i}} \right \vert$
+ RMSE (Root Mean Squared Error) = $\sqrt{MSE}$
+ R-squared (Coefficient of determination) = $1 - \frac{\sum_{i=1}^{n}(y_{i} - \hat{y_{i}})^{2}}{\sum_{i=1}^{n}(y_{i} - \bar{y_{i}})^{2}} = 1 - \frac{SSE}{SST} = \frac {SSR}{SST}$

+ 참고
  + SSE(Sum of Squares Error, 관측치와 예측치 차이): $\sum_{i=1}^{n}(y_{i} - \hat{y_{i}})^{2}$
  + SSR(Sum of Squares due to Regression, 예측치와 평균 차이): $\sum_{i=1}^{n}(\hat{y_{i}} - \bar{y_{i}})^{2}$
  + SST(Sum of Squares Total, 관측치와 평균 차이): $\sum_{i=1}^{n}(y_{i} - \bar{y_{i}})^{2}$ , SSE + SSR

<br/>

## 과적합(Overfitting)과 과소적합(Underfitting)

**일반화**  
모델이 처음 보는 데이터에 대해 정확하게 예측할 수 있으면 이를 훈련 세트에서 테스트 세트로 일반화 되었다고 함  

+ 과적합은 모델이 훈련데이터에만 특수한 성질을 과하게 학습해 일반화를 못해 결국 테스트데이터에서 오차가 커지는 현상을 말합니다
+ 반대로 과소적합은 훈련데이터에 과적합도 못하고 일반화 성질도 학습하지 못해, 훈련/테스트 데이터 모두에서 오차가 크게 나오는 경우를 말합니다.

## 분산/평향 트레이드 오프

+ 분산이 높은경우는, 모델이 학습 데이터의 노이즈에 민감하게 적합하여 테스트데이터에서 일반화를 잘 못하는 경우 즉 과적합 상태입니다.
+ 편향이 높은경우는, 모델이 학습 데이터에서, 특성과 타겟 변수의 관계를 잘 파악하지 못해 과소적합 상태입니다.

## 원핫 인코딩

원-핫 인코딩은 단어 집합의 크기를 벡터의 차원으로 하고, 표현하고 싶은 단어의 인덱스에 1의 값을 부여하고, 다른 인덱스에는 0을 부여하는 단어의 벡터 표현 방식입니다. 이렇게 표현된 벡터를 원-핫 벡터(One-Hot vector)라고 합니다.

원-핫 인코딩을 두 가지 과정으로 정리해보겠습니다.
1. 각 단어에 고유한 인덱스를 부여합니다. (정수 인코딩)
2. 표현하고 싶은 단어의 인덱스의 위치에 1을 부여하고, 다른 단어의 인덱스의 위치에는 0을 부여합니다.


## 특성 선택

## Ridge Regression
Ridge 회귀를 사용하는 이유 : 과적합을 줄이기 위해서 사용  
Ridge 회귀는 **편향을 조금 더하고, 분산을 줄이는** 방법으로 정규화(Regularization)를 수행

### RidgeCV를 통한 최적 패널티(alpha, lambda) 검증

---

## 로지스틱회귀(Logistic Regression)

회귀를 사용하여 데이터가 어떤 범주에 속할 확률을 0에서 1 사이의 값으로 예측하고 그 확률에 따라 가능성이 더 높은 범주에 속하는 것으로 분류해주는 지도 학습 알고리즘이다.  

## Log odds

## Sigmoid Function

## Log Loss(로그 손실)

## Classification Threshold (임계값)


