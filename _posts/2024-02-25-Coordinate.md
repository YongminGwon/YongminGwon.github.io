---
layout: posts
title: Graphics
---
Local space -> World space -> View space -> Canonical space로 변환

MVP matrix(model view projection matrix)

Depth Buffer
- z 버퍼라고도 함
- 깊이 테스트
	- 픽셀의 값을 업데이트하기 전 그리려는 픽셀의 z값과 깊이버퍼에 저장된 해당 위치의 z값을 비교해봄

OpenGL Depth Buffer 초기값은 1
1이 가장 뒤 0이 가장 앞 (왼손 좌표계)
glEnable(GL_DEPTH_TEST) / glDisable(GL_DEPTH_TEST)
glDepthFunc()로 깊이테스트 통과 조건 변경 가능
기본