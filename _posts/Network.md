---
categories:
  - Post
  - Layout
---

```
// 소켓 생성
int socket(int domain, int type, int protocol);

// 소켓에 주소 할당
int bind(int sockfd, struct sockaddr *myaddr, int addrlen);

// 연결 요청을 받을 수 있게 만들기
int listen(int sockfd, int backlog);

// 연결 요청 받기
int accept(int sockfd, struct sockaddr *addr, int *addrlen);
```

### 클라이언트 소켓 구현

connect 함수로 서버에 요청을 보내는 함수

```
int connect(int sockfd, struct sockaddr *serv_addr, int addrlen);
```

1. 소켓 생성
2. connect로 서버에 접속 시도
3. 데이터 교환

### 디스크립터와 핸들

시스템과 클라이언트가 소통할때 생성하는 숫자로 리눅스에서는 디스크립터, 윈도우에서는 핸들로 불린다.

```
// 파일을 여는 함수
int open(const char *path, int flag);

// 파일을 닫는 함수
int close(int fildes);
// fildes : 닫아줄 파일의 파일 디스크립터.

// 데이터 쓰기
ssize_t write(int fildes, const void * buf, size_t nbytes);
```

- fildes : 데이터 전송 영역을 나타내는 파일 디스크립터.
- buf : 전송할 데이터를 가지고 있는 버퍼의 포인터.
- nbytes : 전송할 데이터의 바이트 수.

### 윈도우에서의 윈속 프로그래밍

winsock2.h 헤더를 include 할 때 ws2_32.lib 라이브러리를 링크 시켜야 하는데 이를 편하게 하기 위한 매크로는
```
#pragma comment(lib, "ws2_32.lib")
```
다음과 같다.

윈속을 초기화 할 때 반드시 WSAStartup 함수를 호출 해야 한다.

```
#include <winsock2.h>

int WSAStartup(
	WORD wVersionRequested,
	LPWSADATA lpWSAData
);
```

- wVersionRequested : 프로그램에서 요구하는 윈속의 최상위 버전을 알려주기 위해 사용됨. WORD는 16비트 unsigned int로 상위 8비트는 부버전 하위 8비트는 주버전을 표시한다. 값 설정이 까다로우므로 MAKEWORD라는 매크로 함수가 제공된다.
- lpWSAData : WSADATA타입 변수의 포인터를 인자로 전달한다. 함수 호출이 끝나면 WSADATA 변수에 로딩한 DLL에 대한 정보가 채워진다. 일반적으로 많이 사용되지는 않는다.

MAKEWORD 함수

```
#include <winsock2.h>

WORD MAKEWORD(
	BYTE bLow,
	BYTE bHigh
);
```

bLow에 하위 8비트에 채워질 데이터를 인자로 넣고 bHigh에 상위 8비트에 채워질 데이터를 전달하면 원하는 WORD 값을 얻게 된다.
ex) WORD(2, 2)를 호출하면 0x0202가 리턴된다.

```
int main(int argc, char **argv)
{
	WSADATA wsaData;
	if(WSAStartup(MAKEWORD(2, 2), &wsaData) ! = 0)
		error_handling("WSAStartup() error!");
}
```
버전 2.2를 기반으로 할때 일반적인 시작 코드.

종료 코드
```
int WSACleanup(void);
```

### 소켓의 생성

```
#include <winsock2.h>

SOCKET socket(int af, int type, int protocol);
```

### 주소와 포트 할당

```
#include <winsock2.h>

int bind(SOCKET s, const struct sockaddr FAR * name, int namelen);
```

### '연결 요청 대기 상태'로의 진입

```
#inlcude <winsock2.h>

int listen(SOCKET s, int backlog);
```



### 연결 수락

```
#include <winsock2.h>

SOCKET accept(SOCKET s, struct sockaddr FAR *addr, int FAR *addrlen);
```

* FAR의 경우에는 과거 16비트 windows 프로그래밍에서 사용되었던 키워드로 포인터가 세그먼트를 초과할 수 있도록 하기 위해 사용되었다. 현대는 필요없고 사용해도 컴파일 시 무시된다.

## 소켓 함수

소켓함수의 인자들은 세개로 첫번째는 프로토콜 체계 두번째는 소켓의 타