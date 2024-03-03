---
layout: posts
title: Graphics Advanced_OpenGL(2)
---
## Anti-Aliasing

rasterization할 때 경계발생으로 계단현상이 일어나는것을 처리하는것

예전 기법 : Supersampling Anti-Aliasing (SSAA)

OpenGL의 기법 : MSAA(Multisample Anti-Aliasing)

MSAA의 아이디어
- 한 픽셀이 삼각형 안에 들어갈지 말지를 여러위치에 대해서 조사
- 삼각형 안에 포함된 샘플의 개수에 따라 알파값을 조절

# Advanced Lighting



## Blinn-Phong Shading

Phong Shading의 문제점
- Specular shininess 값이 작을 경우 highlight 부분이 잘리는 현상
- Specular를 계산할 때 view와 reflection간의 각도가 90보다 커질때 cutoff가 발생

Blinn의 방식 
- view와 light를 이등분하는 halfway 벡터와 normal 벡터의 사잇각으로 계산.
## Shadow Map

- 가장 많이 사용되는 그림자 렌더링 알고리즘
- 구현 난이도도 어렵지 않으며 성능을 많이 잡아먹지도 않는다.
- 고급 알고리즘으로의 확장이 편하다
	- omnidiractional shadow map
	- cascaded shadow map

- 빛의 시점에서 렌더링을 해본다.
- 빛이 볼 수 있는 부분은 그림자가 지지않고 볼수있는 부분은 그림자가 진다.

light source의 위치에서 물체들의 depth map만 렌더링하고 이를 바탕으로 빛을 받는지 아닌지 판단하여 그림자를 그린다.

## Shadow Acne
Shadow Map 그렸을 때 Shadow acne가 일어날 수 있다.
shadow map의 해상도가 한정적이기 때문
bias를 더한 값을 비교 수치로 사용해서 해결
Dynamic shadow bias
- light direction과 surface normal 간의 각도가 크면 bias도 크게 만들기

## Peter panning 현상

Dynamic shadow bias를 적용하였을 때 bias가 크면 그림자가 멀리에서부터 생기는 현상
- shadow bias값을 잘 조절하거나
- face culling을 사용해 뒷면만 그리도록 함

## PCF (Percentage Closer Filtering)
- shadow map으로부터 depth값을 여러개 수집해 계산된 shadow 값의 평균을 사용
- directional light에 사용

point light는 여러 depth map을 그려야하기에
## Omni-directional shadow map
사용
depth cube map을 생성하는 방식

## Normal Mapping

해상도 좋은 텍스처라도 요철을 표현하려면 버텍스 갯수를 늘려야하는데 노말매핑으로
이를 커버할 수 있음
normal map은 픽셀의 rgb 값에 normal xyz값이 저장되어 있다.

## Tangent Space

## Parallex Mapping

normal mapping은 큰 깊이감은 만들 수 없고 경계면에서의 입체감을 가질수는 없다.
- View vector, height map이 주어졌을 때 normal mapping은 a 위치를 기준으로 light를 계산하여 실제 위치 B를 예측하는 방법으로 mapping하는 형식

## HDR

그래픽 하드웨어가 다룰 수 있는 색상값의 범위
- 0.0 ~ 1.0 사이의 값
- fragment shader에서 1.0보다 큰 값이 들어오면 clamp 처리됨
