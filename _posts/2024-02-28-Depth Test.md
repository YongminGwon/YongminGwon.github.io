---
layout: posts
title: Graphics Depth Test
---
Depth buffer : 깊이값을 저장하는 버퍼
Depth test 
- 그리려고 하는 픽셀의 깊이값과 버퍼에 저장된 깊이값을 비교
- 비교에 성공하면 그리고 아니면 그리지 않음

Stencil Buffer
- color/depth 외에 특정 픽셀에만 그림을 그리도록하는 용도의 8bit 정수형 버퍼
- depth test를 하기전에 stencil test를 진행

```
glEnable(GL_STENCIL_TEST);
glStencilMask(0xFF);
glStencilFunc(GL_EQUAL, 1, 0xFF);
```

Stencil Operation
```
glStencilOp(sfail, dpfail, dppass)
```
sfail : stencil test가 실패했을시 동작
dpfail : stencil test는 통과했지만 depth test가 실패했을때 동작
dppass: 모두 통과했을 떄 동작

GL_KEEP : 현재의 스텐실 버퍼값 유지
GL_ZERO : 스텐실 버퍼를 0으로 변경
GL_REPLACE : glStencilFunc를 통해 설정된 값으로 변경
GL_INVERT : 스텐실버퍼값을 bitwise invert 시킴
GL_INCR :
GL_INCR_WRAP : 
GL_DCR :
GL_DECR_WRAP : 