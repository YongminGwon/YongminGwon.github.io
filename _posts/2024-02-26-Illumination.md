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
- normal을 다시 normalize하는 이유
	- raterization되는 과정에서 선형보간이 진행될때 더이상 unitvector가 아닐수있어서.
Specular Light
- 반사광
- 빛이 물체 표면에 부딪혀 반사되는 광원
- reflect = 2 * dot(light, normal) * normal - light
- specular = dot(view, reflect)

Directional Light

Point Light

