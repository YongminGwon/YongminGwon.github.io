---
layout: posts
title: Graphics Advanced_OpenGL
---
Face culling

- 삼각형을 이루는 점의 순서에 따라 앞면 뒷면 결정

```
glEnable(GL_CULL_FACE); // face culling 활성화 
glDisable(GL_CULL_FACE); // face culling 비활성화 
glFrontFace(GL_CCW); // CCW 방향의 면을 앞면으로 설정 
glCullFace(GL_BACK); // 뒷면을 그리지 않기 
glCullFace(GL_FRONT); // 앞면을 그리지 않기
```


