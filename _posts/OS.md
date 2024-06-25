---
title: Operating System
---
## 다루는 것들

Windows Operating System Programming에 대해 다룹니다.

리눅스는 이후에 다룰 수도 있겠지만 당장은 Windows OS에 대해 다루겠습니다.

널널한 개발자님의 시스템 프로그래밍 강의와 뇌를 자극하는 시스템 프로그래밍 책을 참고하여 

작성합니다.


## 핸들러

개념적인것 일반적으로 포인터로 나타난다. 리눅스에서는 디스크립터로 표현된다.


## 보안 기술자 (Security Descriptor)

검색시에 보안 기술자 보다는 영어로 검색하거나 보안 설명자로 검색할 경우 자료가 더 잘 나온다.

보안 객체에 대한 정보
- 객체의 소유자 및 그룹
- 보호 속성(Protection attributes)
- 감사 정보(Audit information)
파일이나 폴더 생성 시 접근 권한에 관한 정보가 함께 생성된다.

대표적인 보안 객체
- 파일과 폴더
- 프로세스와 스레드
- 파일 매핑 객체
- 파이프
- 토큰
- 윈도우 스테이션 및 데스크톱
- 레지스트리
- 서비스
- 프린터
- 네트워크 공유자원
- 이벤트, 뮤텍스, 세마포어 (Kernel object)

## DACL(Discretionary Access Control List)

보안 객체에 대한 접근 허용 차단 정보를 가진 데이터 구조
ACL의 리스트
ACL은 ACE(Access Contol Entry)의 리스트

리스트의 리스트의 리스트인것 (DACL(ACL(ACE)))

ACE
- 윈도우 시스템에서 접근 제어를 위한 기본 정보
- 권한에 따라 접근을 제한한다는 것은 ACE를 수정 편집하는것
- ACE의 핵심 정보는 SID(Security IDentifier) 사용자나 그룹을 식별
SACL
- 보안 객체에 대한 접근 로그를 남기는 근거 정보
- 권한없는 사용자의 쓰기 시도 발생 시 로그 저장

## 