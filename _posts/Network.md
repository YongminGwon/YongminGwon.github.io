
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

winsock2.h 헤더를 include 할 때 ws2_32.lib 라이브러리를 링크시켜야하는데 이를 편하게 하기위한 매크로는
```
#pragma comment(lib, "ws2_32.lib")
```
다음과 같다.

윈속을 초기화 할 때 반드시 WSAStartup 함수를 호출해야한다.

```
#include <
```