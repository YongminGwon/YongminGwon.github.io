---
layout: posts
title: Graphics Illumination
---
Local/Global Illumination
반사광 : 광원이 물체에 반사되어 발생한 빛
Local : 반사관 고려 X
Global : 반사광 고려

phong reflection model
- 빛과 물체 간의 색상 결정을 3가지료 나눠서 표현
- ambient(주변광), diffuse(분산광), specular(반사광)

Ambient Light
- 물체가 기본적으로 받는 빛

Diffuse Light
- 빛이 물체에 부딫혔을 때 모든 방향으로 퍼지는 빛
- diffuse = dot(light, normal) 
	- 사잇각을 쓰므로

Specular Light
- 