
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
```

