---
title: "Basic Mathematics"
date: 2019-07-21T18:17:00-04:00
categories:
  - directX 12
tags:
  - study
  - math
---

## 벡터 대수
#### 좌표계
왼손잡이 좌표계, 오른손잡이 좌표계(z축의 방향이 반대)

#### 단위벡터(unit vector)

크기가 1인 벡터

#### 정규화(normalization)

임의의 벡터를 단위 벡터로 만드는 것

#### 내적(inner product)

스칼라값을 내는 벡터 곱셈의 일종

대응되는 성분들의 곱들의 합

Θ는 벡터 u와 v사이의 0 ≤ Θ ≤ π를 만족하는 각도이다.

두 벡터의 내적 값이 0이면 두 벡터는 직교이다.

두 벡터의 값이 0보다 크다면 두 벡터 사이의 각도는 예각을 이룬다.

#### 정규직교(orthonormal)집합

모든 벡터가 단위 길이이고 서로 직교인 벡터 집합

#### 직교화(orthogonalization)

주어진 벡터 집합이 정규직교에 가깝지만 완전히 정규직교는 아닌 집합을 정규직교 벡터 집합으로 만드는 것

#### 그람-슈미트 직교화

집합의 모든 벡터를 정규화하는 공정

![gram-schmidt](/assets/images/gram-schmidt.jpg)

#### 외적(outer product)

외적의 결과는 벡터이다.

두 3차원 벡터 u와v의 외적을 취하면 u와 v 모두에 직교인 벡터 w가 나온다.

#### 위치벡터

특정 좌표계를 기준으로 표준 위치에 있는 벡터를 3차원 공간 안의 한 위치를 나타내는 데 사용한다.

벡터의 방향이나 크기가 아니라 벡터의 머리 끝의 좌표

점을 벡터로 표현하는 방식

![vector1](/assets/images/vector1.jpg)

<br>

### DirectXMath 라이브러리의 벡터
#### SIMD

128비트 너비의 SIMD레지스터를 이용해서 32비트 float 또는 int 네개를 단번에 처리할 수 있다.

#### XMVECTOR

지역 변수나 전역변수에 XMVECTOR사용

XMVECTOR 인스턴스들로 계산을 수행

#### XMFLOAT2, XMFLOAT3, XMFLOAT4

클래스 자료 멤버에는 XMFLOAT2, XMFLOAT3, XMFLOAT4를 사용

계산을 수행하기 전에 XMFLOATn을 XMVECTOR로 변환하여 계산 수행

<br>

## 행렬 대수

정방행렬, 단위행렬, 행벡터, 열벡터

#### 전치행렬

행렬의 행들과 열들을 맞바꾼것

#### 행렬식(determinant)

정방행렬을 입력받아서 실숫값을 출력하는 특별한 함수

#### 소행렬

A의 i번째 행과 j번째 열을 삭제해서 나온 행렬

#### 가역행렬

역행렬이 존재하는 행렬

#### 여인수

A가 n x n 행렬일때 Cij = (-1)^(i+j)detAij는 Aij의 여인수이다.

#### 여인수행렬

A의 각 성분 Cij를 계산해서 해당 ij번째 위치에 배치핸 행렬 Ca가 행렬 A의 여인수행렬

#### 딸림행렬(adjoint matrix, 수반행렬)

여인수행렬의 전치행렬

<br>

### DirectXMath의 행렬
#### XMMATRIX

SIMD활용을 위해 XMVECTOR 인스턴스 네개를 사용

<br>

## 변환

선형변환(linear transformation), 비례행렬(scaling matrix), 회전

![matrix](/assets/images/matrix.jpg)

#### 아핀변환

선형변환에 이동변환을 결합한 것

#### 동차좌표

점과 벡터를 동일한 방식으로 다룰 수 있게 해주는 것

3차원 벡터에 w성분을 추가한 네값쌍의 형태

벡터을 나타내는 동차좌표 (x, y, z, 0)

점을 나타내는 동차좌표 (x, y, z, 1)

#### 변환들의 합성

변환들은 행렬이므로 결합법칙을 만족하므로 변환들을 하나로 합칠 수 있다.

이 경우 3차원 물체에 변환을 여러개 적용할 때에 행렬 곱셈 회수를 줄일수 있다.

단, 결합 순서가 달라질 경우 결과도 달라진다.

## 참고도서

DirectX 12를 이용한 3D게임 프로그래밍 입문
