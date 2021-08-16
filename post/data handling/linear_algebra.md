---
layout : post
title : linear algebra
description :
parent : data handling
has_children: false
nav_order : 6
use_math : true
---

# linear algebra (선형대수)
{: .text-center}

## 스칼라, 벡터
+ 선형대수를 구성하는 기본 단위
+ 벡터는 파이썬에서는 주로 list로 사용, 데이터셋을 구성하는 데이터프레임의 행/열로써 사용되기도 함

### 스칼라
단일 숫자, 변수에 저장 할 때는 일반적으로 소문자를 이용하여 표기함

### 벡터
n 차원의 벡터는 **컴포넌트**라 불리는 n개의 원소를 가지는 **순서를 갖는** 모음

### 벡터의 크기 (Magnitude, Norm, Length)
{: .bg-yellow-300}

모든 원소의 제곱을 더한 후 루트를 씌운 값

> $ \vert x \vert \geq 0$  
> 
> $ \Vert x \Vert = 0$ (모든 원소가 0)  
> 
> 삼각 부등식: $\Vert x \Vert + y \Vert \leq \Vert x \Vert + \Vert y \Vert $

### 벡터의 내적 (Dot Product)

두 벡터의 내적은 각 구성요소를 곱한뒤 합한 값과 같다  
벡터의 내적을 위해서는 두 벡터의 길이가 반드시 동일 해야 한다.  
내적이 0 일 경우 두 벡터는 직각이다.  

## 메트릭스

### 정사각 메트릭스

**identity (단위 메트릭스)**  
+ Diagonal 매트릭스(대각 매트릭스) 중에서 모든값이 1인 경우.
+ 임의의 정사각 매트릭스에 단위 행렬을 곱하면 그 결과값은 원본 정사각 매트릭스
+ 임의의 매트릭스에 대해 곱했을때 단위 매트릭스가 나오게 하는 행렬을 역행렬(inverse) 라고함

**Symmetric(대칭)** 대각선을 기준으로 위 아래 값이 대칭인 경우

### Determinant (행렬식)

모든 정사각형 매트릭스가 갖는 속성으로 ded(a) 혹은 $\vert x \vert$로 표기

### Inverse (역행렬)

+ 역행렬을 계산하는 방법은 여러가지가 있으며, 행렬의 역수와 같이 표현 할 수 있음

<br/>
**매트릭스에 역행렬을 곱하면**  
  단위 매트릭스가 된다.

<br/>
**행렬식이 0인 경우**  
그 행렬의 역행렬은 존재하지 않는다는 의미


