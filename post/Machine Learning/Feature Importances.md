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

예측 성능이 조금 낮은 약한 분류기들을 조합하여  
좀 더 좋은 성능을 발휘하는 하나의 **강한 분류기**를 만드는 방법

### 부스팅과 배깅의 차이점 (in 아상블 모델)
+ 부스팅
  + 순차적 샘플링
  + 이전 모델의 오류가 다음 모델에 영향을 준다
  + ada boosting, gradient boosting
  + 이상치에 취약 할 수 있다
+ 배깅
  + 독립적, 병렬적 샘플링
  + 모델간의 간섭이 없다
  + 랜덤포레스트

**부스팅 모델은 분류/회귀 문제 모두 사용할 수 있다.**

---
### 1. AdaBoost

**stump**로 구성.  
하나의 stump에서 발생한 애러가 다음 stump에 영향을 준다. 이런식으로 여러 stump가 순차적으로 연결되어 최종결과를 도출한다.  


### 2. Gradient Boost

stump나 tree가 아닌 **leaf**부터 시작.  
이 leaf는 타겟값에 대한 초기 추정값을 나타낸다. 보통은 초기 추정값을 평균으로 정한다.  그 다음은 AdaBoost와 동일하게 이전 tree의 error는 다음 tree에 영향을 줍니다. 하지만 AdaBoost와 다르게 stump가 아닌 tree로 구성되어 있습니다. 보통은 leaf가 8개에서 32개되는 tree로 구성합니다.  

### 3. XG Boost

GBM은 residaul을 줄이는 방향으로 weak learner를 결합해 강력한 성능을 자랑하지만, 해당 train data에 residual을 계속 줄이니까 overfitting 되기 쉽다는 문제점이 있다. 이를 해결하기 위해 XGBoost는 GBM에 regularization term을 추가한 알고리즘이다. 또한 다양한 loss function을 지원해 task에 따른 유연한 튜닝이 가능하다는 장점이 있다.

---

하이퍼파라미터 튜닝
{: .label .label-green}

**XGBoost**
+ learning_rate (높을경우 과적합 위험이 있다)
+ max_depth (낮은값에서 증가시키며 튜닝, 너무 깊어지면 과적합위험, -1 설정시 제한 없이 분기, 특성이 많을 수록 깊게 설정)
+ n_estimators (너무 크게 주면 긴 학습시간, early_stopping_rounds와 같이 사용)
+ scale_pos_weight (imbalanced 문제인 경우 적용시도)





