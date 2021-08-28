---
layout : post
title : Find ML problem
description :
parent : Machine Learning
has_children: false
nav_order : 5
use_math : true
date : 21-08-28
# last_modified_date : 2021-08-27
---

# Find ML problem
{: .text-center}

## 데이터 과학자 실무 프로세스

1. 비즈니스 문제
   1. 실무자들과 대화를 통해 문제 발견
2. 데이터 문제
   1. 문제와 관련된 데이터를 발견
3. 데이터 문제 해결
   1. 데이터 처리 시각화
   2. 머신러닝/통계
4. 비즈니스 문제 해결
   1. 데이터 문제 해결을 통해 실무자들과 함께 해결

---

## 예측해야 하는 타겟을 명확히 정하고 분포를 살핌
### 지도학습에서는 예측할 타겟을 먼저 정한다
### 데이터 특성들을 살펴보고 간단히 전처리

---
## 정보의 누수(leakage)가 없는지 확인
---

### 문제에 적합한 평가지표를 선택

**분류 와 회귀** 모델의 평가지표는 완전히 다르다.

**분류 문제**

분류문제에서 타겟 클래스비율이 70% 이상 차이날 경우에는 정확도만 사용하면 판단을 정확히 할 수 없음  
**정밀도, 재현율, ROC curve, AUC** 등을 같이 사용

### 불균형 클래스

+ 대부분 scikit-learn 분류기들은 class_weight 와 같은 클래스의 밸런스를 맞추는 파라미터를 가지고 있음

---

**회귀문제**

**타겟의 분포를 주의깊에 살펴야함**

### 로그변환(Log-Transform)


---
# Data Wrangling
{: .text-center}





