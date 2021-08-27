---
layout : post
title : Tree Based Model
description :
parent : Machine Learning
has_children: false
nav_order : 3
use_math : true
date : 21-08-25
# last_modified_date : 2021-08-06
---

# Tree Based Model
{: .text-center}

<!-- 사이킷런 파이프라인(pipelines) 을 이해하고 활용 할 수 있습니다.
사이킷런 결정트리(decision tree) 를 사용할 수 있습니다.
결정트리의 특성 중요도(feature importances) 를 활용할 수 있습니다.
결정트리 모델의 장점을 이해하고 선형회귀모델과 비교할 수 있습니다. -->

## 사이킷런 파이프라인 (Pipelines)

+ 여러 ML모델을 손쉽게 연결 시킬 수 있음
+ 그리드 서치를 통해 여러 하이퍼 파라미터를 쉽게 연결 할 수 있음

```python
from category_encoders import OneHotEncoder
from sklearn.impute import SimpleImputer
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression
from sklearn.pipeline import make_pipeline

pipe = make_pipeline(
    OneHotEncoder(), 
    SimpleImputer(), 
    StandardScaler(), 
    LogisticRegression(n_jobs=-1)
)
```
LogisticRegression 의 n_jobs 는 정수로 지정, multi_class='ovr'인 경우 클래스를 병렬화할 때 사용되는 CPU 코어 수”  
-1은 모든 프로세서를 사용하는 것을 의미

<br/>

## 결정트리 (Decision Tree)

>결정 트리 학습법은 데이터 마이닝에서 일반적으로 사용되는 방법론으로, 몇몇 입력 변수를 바탕으로 목표 변수의 값을 예측하는 모델을 생성하는 것을 목표.  
>결정 트리 학습법은 지도 분류 학습에서 가장 유용하게 사용되고 있는 기법 중 하나이다. 이 글에서는 모든 속성들이 유한한 이산값들로 구성된 정의역을 가지고 있으며, 분류를 단일 대상 속성으로 지니고 있다고 간주한다. 분류의 정의역의 각 원소들은 클래스라고 불린다. 결정 트리 또는 분류 트리의 모든 내부 노드들에는 입력 속성이 일대일로 대응된다. 트리의 내부 노드에 연결된 가지에는 속성이 가질 수 있는 값들이 표시되며, 잎 노드에는 클래스 또는 클래스의 확률 분포가 표시된다.

+ 분류와 회귀 문제에 모두 적용 가능
+ 분류 트리 분석은 예측된 결과로 입력 데이터가 분류되는 클래스를 출력
+ 회귀 트리 분석은 예측된 결과로 특정 의미를 지니는 실수값을 출력한다. 
+ 분류 과정은 새로운 데이터가 특정 말단 노드에 속한다는 정보를 확인한 뒤 말단 노드의 빈도가 가장 높은 범주로 데이터를 분류.
+ 분류과정을 직관적으로 확인 가능한 장점이 있음.


## 결정트리 학습 알고리즘
+ 지니불순도(Gini Impurity or Gini Index): ${\displaystyle {I}_{G}(p)=\sum _{i=1}^{J}p_{i}(1-p_{i})=1-\sum _{i=1}^{J}{p_{i}}^{2}}$
+ 엔트로피(Entropy): ${\displaystyle \mathrm {H} (T)=\operatorname {I} _{E}\left(p_{1},p_{2},...,p_{J}\right)=-\sum _{i=1}^{J}{p_{i}\log _{2}p_{i}}}$

<br/>
> 결정트리 학습 알고리즘은 과적합이 일어나기 쉽다.

트리의 복잡도를 줄이기 위해 사용되는 **하이퍼 파라미터**
+ min_samples_split
+ min_samples_leaf
+ max_depth

## 특성 중요도 (feature importance)
선형 모델에서는 특성과 타겟의 관계를 확인하기 위해 회귀 계수 (coefficients)  
결정트리에서는 대신 **특성 중요도**를 확인 할 수 있음  
특성 중요도는 항상 양수값을 가짐

**결정트리모델은 선형모델과 달리 비선형, 비단조(non-monotonic), 특성상호작용(feature interactions) 특징을 가지고 있는 데이터 분석에 용의함**  

    특성상호 작용
    특성들끼리 서로 상호작용을 하는 경우.  
    회귀 분석에서는 서로 상호작용이 높은 특성들이 있으면 
        개별 계수를 해석하는데 어려움이 있고 학습이 올바르게 되지 않을 수 있음  
    트리모델은 이런 상호 작용을 자동으로 걸러내는 특징이 있음

# 랜덤포레스트 (Random Forests)
{: .text-center}

**랜덤포레스트는 앙상블 방법이다.**

일련의 예측기(분류나 회귀 모델)로 부터 예측을 수집하면 가장 좋은 모델 하나보다 더 좋은 예측을 얻을 수 있다.  
**일련의 예측기를 앙상블**이라 부르며, 이를 **앙상블 학습**이라고 하며, 앙상블 학습 알고리즘을 **앙상블 기법 혹은 방법**이라 부른다.  
랜덤포레스트는 결정트리를 기본 모델로 사용하는 앙상블 방법이라 할 수 있다.  
결정트리들은 **독립적**으로 만들어 지며, 각각 랜덤으로 예측하는 성능보다 좋을 경우, 랜덤포레스트는 결정트리보다 성능이 좋다.  

### 배깅

Bagging이란 bootstrap aggregating을 의미한다. 그리고 bootstrap이란 복원추출을 의미한다. 즉 복원추출한 것들을 합친다는 것이다.

### 부트스트랩

앙상블 세트에 사용하는 작은 모델들은 부트스트래핑이라는 샘플링 과정으로 얻은 부트스트랩 세트를 사용해 학습을 한다.  
즉 원본데이터에서 **복원추출** 한다.

**추출되지 않는 36.8%의 샘플이 Out-Of-Bag 샘플이며 이것을 사용해 모델을 검증할 수 있다.**

부트스트랩세트로 만들어진 기본모델들을 합치는 과정을 **Aggregation** 이라고 한다.

+ 회귀 문제의 경우 기본 모델 결과들의 **평균**으로 결과를 내고
+ 분류 문제일 경우 **다수결**로 가장 많은 모델들이 선택한 범주로 예측

**랜덤포레스트는 기본모델들의 트리를 만들 때 무작위로 선택한 특성세트를 사용**

+ 결정트리에서 분할을 위한 특성을 선택할 때, 모든 특성(n개)을 고려하여 최적의 특성을 고르고 분할하였습니다.
+ 하지만 랜덤포레스트에서는 특성 n개 중 일부분 k개의 특성을 선택(sampling) 하고 이 k개에서 최적의 특성을 찾아내어 분할합니다. 이때 k개는 일반적으로 $log_2 n$ 를 사용합니다.

<br/>

## 범주형 자료의 다른 인코딩 방법인 순서형(ordinal) 인코딩







