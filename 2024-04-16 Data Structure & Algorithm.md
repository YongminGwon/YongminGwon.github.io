
## Contiguous Data Structures

배열이 이에 속하며 원소로의 접근은 O(1)의 Time complexity

동적 배열을 할당할 때 int* arr = new int[size]; 의 형식으로 할당한다.

정적 배열은 stack 메모리에 할당 동적 배열은 heap에 할당.

배열에서 원소에 접근할 때 인접 원소도 cache로 가져온다.

이를 cache locality(캐시 지역성)이라고도 한다.

## Linked Data Structures

head에서 시작하여