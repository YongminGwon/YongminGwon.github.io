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
