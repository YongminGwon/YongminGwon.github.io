
멀티스레드를 사용하면 좋은 경우
1. 오래 걸리는 일 하나와 빨리 끝나는 일 여러개를 같이 할 때
2. 긴 처리를 진행하는동안 다른 짧은 일을 같이 해야 할 때
3. 기기에 있는 CPU를 모두 활용해야 할 때

1번의 예 : 게임 프로그램의 로딩 
2번의 예 : 디스크에 엑세스 할 때 기다리는 시간동안 남는 CPU를 사용
3번의 예 : 

멀티스레드를 남용하면 안좋은 이유
- 컨테스트 스위칭에도 자원이 들어서 그것또한 고려해야함

CPU와 스레드의 관계는 비둘기 집의 원리와 같다. 다만 Runnable(실행중)인 CPU

와 상관관계가 있다. 

Runnable Suspended Terminated 의 세가지 상태의 스레드가 있다.

스레드 생성에는 CreateThread()와 _beginthreadex가있다.
