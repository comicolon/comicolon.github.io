---
layout : post
title : clustering
description :
parent : data handling
has_children: false
nav_order : 9
use_math : true
date : 21-08-21
# last_modified_date : 2021-08-06
---

# Clustering
{: .text-center}

## Scree Plots
x축에 주성분을 놓고 y축에 해당 주성분에 대응하는 고유값을 연결한 그림으로 그래프가 완만해지는 부분 이전까지의 주성분을 활용

## Machine Learning (개요)

+ 지도 학습은 트레이닝 데이터에 **라벨(답)**이 있을 때 사용 할 수 있음
  + 분류 : 주어진 데이터의 카테고리 혹은 클래스 예측을 위해 사용
  + 회귀 : continuous 한 데이터를 바탕으로 결과를 예측 하기 위해 사용

+ 비지도 학습
  + 클러스터링 (Clustuering) 데이터의 연관된 feature를 바탕으로 유사한 그룹을 생성
  + 차원축소 (Dimensionality Reduction) : 높은 차원을 갖는 데이터셋을 사용하여 차원을 줄이는 방법
  + 연관 규칙 학습 (Association Rule Learning) : 데이터셋의 feature들의 관계를 발견하는 방법

+ 강화 학습 : 기계가 좋은 행동에 대해 보상, 그렇지 않은 행동에 처벌 이라는 피드백으로 행동에 대해 학습해 가는 방법

## Clustering

Unsupervised Learning Algorithm의 한 종류  
데이터를 보다 잘 이해하기 위해서.

1. 하나의 군집에 있는 각 데이터의 포인트가 비슷하고
2. 다른 군집에 있는 데이터와는 다르게.

## Clustering의 종류

+ Hierarchical (계층적)
  + Agglomerative: 개별 포인트에서 시작후 점점 크게 합쳐감
  + Divisive: 한개의 큰 cluster에서 시작후 점점 작은 cluster로 나눠감
+ Point Assignment
  + 시작시에 cluster의 수를 정한 다음, 데이터들을 하나씩 cluster에 배정시킴
+ Hard vs Soft Clustering
  + Hard Clustering에서 데이터는 하나의 cluster에만 할당
  + Soft Clustering에서 데이터는 여러 cluster에 확률을 가지고 할당

<br/>
일반적으로 많이 쓰이는 방식은 Euclidean

## K-Means Clustering

### 과정
n-차원의 데이터에 대해서 :

1) k 개의 랜덤한 데이터를 cluster의 중심점으로 설정

2) 해당 cluster에 근접해 있는 데이터를 cluster로 할당

3) 변경된 cluster에 대해서 중심점을 새로 계산

cluster에 유의미한 변화가 없을 때 까지 2-3을 반복

### K-means 에서 K의 결정
+ The Eyeball Method :사람의 주관적인 판단을 통해서 임의로 지정하는 방법

+ Metrics : 객관적인 지표를 설정하여, 최적화된 k를 선택하는 방법
