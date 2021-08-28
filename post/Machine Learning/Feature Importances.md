---
layout : post
title : Feature Importances
description :
parent : Machine Learning
has_children: false
nav_order : 6
use_math : true
date : 21-08-28
# last_modified_date : 2021-08-27
---

# Feature Importances
{: .text.center}

## 모델 해석과 특성 선택을 위한 순열 중요도(Permutation Importances) 계산

### 3가지 특성 중요도
1. Feature Importances(Mean decrease impurity, MDI)
    + sklearn 트리 기반 분류기에서 디폴트로 사용되는 특성 중요도는 속도는 빠르지만 결과를 주의해서 봐야 한다.
2. Drop-Column Importance
    + 이론적으로 가장 좋아 보이지만 매우 느리다.
    + 특성이 n개면  n+1번의 학습이 필요
3. **순열중요도, (Permutation Importance, Mean Decrease Accuracy,MDA)**
    + 기본 특성 중요도와 Drop-column 중요도 중간에 위치하는 특징
    + 관심있는 특성에만 무작위로 노이즈를 주고 예측을 하였을 때 성능 평가지표(정확도, F1, $R^2$ 등)가 얼마나 감소하는지를 측정
    + 노이즈를 주는 간단한 방법이 그 특성값들을 샘플들 내에서 섞는 것
    + **eli5** 라이브러리 이용
  
---

## 부스팅 (Boosting)

### 부스팅과 배깅의 차이점
+ 부스팅
  + 순차적 샘플링
  + 이전 모델의 오류가 다음 모델에 영향을 준다
  + ada boosting, gradient boosting
+ 배깅
  + 독립적, 병렬적 샘플링
  + 모델간의 간섭이 없다
  + 랜덤포레스트

**부스팅 모델은 분류/회귀 문제 모두 사용할 수 있다.**



