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

