
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

