
## Contiguous Data Structures

배열이 이에 속하며 원소로의 접근은 O(1)의 Time complexity

동적 배열을 할당할 때 int* arr = new int[size]; 의 형식으로 할당한다.

정적 배열은 stack 메모리에 할당 동적 배열은 heap에 할당.

배열에서 원소에 접근할 때 인접 원소도 cache로 가져온다.

이를 cache locality(캐시 지역성)이라고도 한다.

## Linked Data Structures

head에서 시작하여 next 포인터를 따라 이동해서 끝에 nullptr로 가는것이 일반적인

형태이다. 변형된 자료구조가 다수 존재한다. 연결리스트 내부를 따라 이동해서 접근

하므로 O(N)의 time complexity를 가진다.

## 빌드 과정
Preprocessor에서 .cpp와 .h로 translation unit이 생성된다.
Compiler가 translation unit을 사용해 .obj를 만든다.
Linker가 .exe를 만든다.

## Constexpr

constexpr을 통해 컴파일 타임에 미리 연산을 할 수 있다.

## Git Hook
으로 Clang Format을 적용하여 깃푸시 할 수 있다.

## Virtual

```
#include <iostream>

class Animal
{
public:
	virtual void speak()
	{
		std::cout << "Animal" << std::endl;
	}
	virtual ~Animal() = default;
};

class Cat : public Animal
{
public:
	void speak() override
	{
		std::cout << "meow" << std::endl;
	}
};

int main()
{
	int i=0;
	std::cin >> i;
	Animal * polyAnimal;
	if(i==1)
	{
	polyAnimal = new Cat();
	}
	else
	{
	polyAnimal = new Animal();
	}
	polyAnimal -> speak();
	delete polyAnimal;
}

```

## Virtual Table

