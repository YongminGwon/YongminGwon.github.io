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


## FrameBuffer

사용과정
- 프레임버퍼 객체 생성
- 렌더버퍼(color/depth/stencil) 생성
- 렌더버퍼를 프레임 버퍼에 연결
- 해당 렌더버퍼의 조합이 프레임버퍼로 사용가능한지 확인

## Post Processing

렌더링된 텍스처에 추가 효과

## Cubemap

2D texture 6장으로 정육면체 형태로 이어붙인 텍스처맵
주변환경을 그리거나 주변환경을 반사시켜 사실감을 높이는데 효과적

sphermap도 있음

skybox는 3D장면의 뒷배경을 채워주는 큰 큐브 적은 정점으로 주변 환경을 그릴 수 있음


## Environment Mapping

주변을 감싸고 있는 환경을 렌더링하고자 하는 오브젝트에 적용하는 방식
- 주변 환경이 물체에 반사되거나
- 주변 환경이 물체에 굴절되서 보이는 경우
- 보통 단독으로 사용하지 않고 일반 쉐이더에 섞어 사용함
- cubemap에서만 색상을 가져오므로 근처의 오브젝트가 비치지않아 비현실적

## Advanced GLSL

interface block

Uniform buffer object

```
unsigned int uboExampleBlock; glGenBuffers(1, &uboExampleBlock); glBindBuffer(GL_UNIFORM_BUFFER, uboExampleBlock); glBufferData(GL_UNIFORM_BUFFER, 152, NULL, GL_STATIC_DRAW); // 152 bytes glBindBuffer(GL_UNIFORM_BUFFER, 0);
```

## Instancing

동일한 오브젝트를 여러번 그릴때 하나의 인스턴스화 시켜놓는것

여러 오브젝트를 한번의 draw call로 그리도록 해주는 기능
cpu-gpu간 통신을 줄여서 성능저하를 방지
