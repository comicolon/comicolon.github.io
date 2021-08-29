---
layout : post
title : interpreting ML Model
description :
parent : Machine Learning
has_children: false
nav_order : 7
use_math : true
date : 21-08-28
# last_modified_date : 2021-08-27
---

# interpreting ML Model

## Partial Dependence Plots(PDP)

+ 복잡한 모델 : 이해하기 어렵지만 성능이 좋다.
+ 단순한 모델 : 이해하기 쉽지만 성능이 부족하다.

부분의존도그림(Partial dependence plots, PDP)을 사용하면 관심있는 특성들이 타겟에 어떻게 영향을 주는지 쉽게 파악할 수 있다.  

+ **선형모델 : 회귀계수(coefficients)**를 사용하면 변수와 타겟 관계를 해석 할 수 있음.
+ **트리모델 : 부분의존그림(PDP)**을 사용하여 개별 특성과 타겟과의 관계를 볼 수 있음.

1특성사용  

**ICE 곡선** : 하나의 관측치에 대해 관심 특성을 변화시킴에 따른 타겟값 변화 곡선이고 이 ICE들의 평균이 PDP 이다.
  
2특성 사용  
3특성 사용  

비교하고자 하는 feature가 많아지면 시각화 할 수 없고, feature 영향력이 과대 평가될 위험이 있다.

---

## SHAP

Shapley Value 는 게임이론을 바탕으로, Game 에서 각 Player 의 기여분을 계산하는 방법이다.  

**하나의 특성**에 대한 중요도를 알기 위해 → 여러 특성들의 조합을 구성하고 → 해당 특성의 유무에 따른 **평균적인 변화**를 통해 값을 계산합니다.  




