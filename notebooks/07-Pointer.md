# 7장 포인터

## 핵심

* 포인터 이해* 문자열 활용

## (C 언어) 물고기 키우기

* 동영상: [(나도코딩 C) 7-1 물고기 키우기](https://www.youtube.com/watch?v=W1zcOFCGqxQ&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=44)

### 게임 설명

* 어항을 클릭해서 물 채우기

---

## (C 언어) 친구들의 주소

* 동영상: [(나도코딩 C) 7-2 친구들의 주소](https://www.youtube.com/watch?v=IxhMzEYB9L0&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=45)

* 예제: 실제 저장된 메모리상의 주소 확인하는 방법

* 앰퍼샌드(ampersand) 기호(`&`): (일반) 변수에 할당된 값이 저장된 메모리 주소를 가리킴
* 주의: 포인터 값을 받는 출력 포맷: `%p` (동영상에서 사용하는 `%d`는 경고 발생시킴)
    * 16진법으로 표현된 메모리 주소 출력

<div align="center"><img src="./images/nado07-c-pointer-1.png" width="250"/></div>

<그림 참조: [SOFT HIVE: C 언어 포인터](https://dasima.xyz/c-pointer/)>

---
```c
#include <stdio.h>

int main()
{
	// 포인터

	// 한 아파트에 철수, 영희, 민수 거주
	// 각각의 문 앞에 '암호'가 걸려 있음.

	// [철수]: 101호 -> 실제 메모리 공간의 주소는 다름
	// [영희]: 201호 -> 실제 메모리 공간의 주소는 다름
	// [민수]: 301호 -> 실제 메모리 공간의 주소는 다름

	int 철수 = 1;  
	int 영희 = 2;
	int 민수 = 3;

	printf("철수네 주소: %p, 암호: %d\n", &철수, 철수);
	printf("영희네 주소: %p, 암호: %d\n", &영희, 영희);
	printf("민수네 주소: %p, 암호: %d\n", &민수, 민수);
}
```

---

### Python 구현


```python

```

---

## (C 언어) 미션맨(포인터)의 등장

* 동영상: [(나도코딩 C) 7-3 미션맨(포인터)의 등장](https://www.youtube.com/watch?v=X1LEhWth4X8&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=46)

* 두 종류의 변수 활용
    * (일반) 변수: 정수, 부동소수점, 문자, 문자열 등 값을 가리키는 변수
    * 포인터 변수: 메모리 주소를 가리키는 변수
        * (일반) 변수가 가리키는 값이 저장된 메모리 주소
        * 배열(어레이), 문자열 등이 저장된 메모리 주소

* 애스터리스크(asterisk) 기호(`*`)의 역할
    * 포인터 변수가 가리키는 주소에 저장된 값을 가리킴

<div align="center"><img src="./images/nado07-c-pointer-2.png" width="550"/></div>

<그림 참조: [SOFT HIVE: C 언어 포인터](https://dasima.xyz/c-pointer/)>

---
```c
	// 미션맨 등장!

	// 첫 번째 미션: 아파트의 각 집에 방문하여 문에 적힘 암호 확인

	int * 미션맨;   // 포인터 변수
	
	// 포인터 변수와, 포인터 변수가 가리키는 주소에 저장된 값 확인
	미션맨 = &철수;  // 철수의 주소
	printf("미션맨이 방문하는 곳의 주소: %p, 암호: %d\n", 미션맨, *미션맨);
	
	미션맨 = &영희;  // 영희의 주소
	printf("미션맨이 방문하는 곳의 주소: %p, 암호: %d\n", 미션맨, *미션맨);
	
	미션맨 = &민수;  // 민수의 주소
	printf("미션맨이 방문하는 곳의 주소: %p, 암호: %d\n", 미션맨, *미션맨);

	// 두 번째 미션: 각 집의 암호에 3 곱하기

	미션맨 = &철수;
	*미션맨 = *미션맨 * 3;
	printf("미션맨이 암호를 바꾼 곳의 주소: %p, 암호: %d\n", 미션맨, *미션맨);

	미션맨 = &영희;
	*미션맨 = *미션맨 * 3;
	printf("미션맨이 암호를 바꾼 곳의 주소: %p, 암호: %d\n", 미션맨, *미션맨);

	미션맨 = &민수;
	*미션맨 = *미션맨 * 3;
	printf("미션맨이 암호를 바꾼 곳의 주소: %p, 암호: %d\n", 미션맨, *미션맨);
```

---

### Python 구현


```python

```

---

## (C 언어) 스파이(또다른 포인터)의 등장

* 동영상: [(나도코딩 C) 7-4 스파이(또다른 포인터)의 등장](https://www.youtube.com/watch?v=Ij_XVWDRznI&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=47)

* 두 개의 포인터가 하나의 메모리 주소 공유
    * 포인터의 주요 역할임. 하지만 매우 어려운 문제 야기 가능
    * 여러 포인터 변수가 하나의 주소를 대상으로 많은 변화를 줄 수 있기 때문.

* 포인터 변수가 가리키는 주소를 저장하는 메모리 공간도 물론 따로 존재
    * 역시 앰퍼샌트 기호(`&`)를 활용하여 확인 가능

<div align="center"><img src="./images/nado07-c-pointer-2a.png" width="550"/></div>

<그림 참조: [SOFT HIVE: C 언어 포인터](https://dasima.xyz/c-pointer/)>

---
```c
	// 스파이
	// - 두 개의 포인터가 동일한 메모리 주소를 가리킬 수 있음.
	// 미션맨이 바꾼 암호에서 2를 빼라!
	int * 스파이 = 미션맨;

	printf("\n ... 스파이가 미션 수행하는 중 ... \n\n");

	스파이 = &철수;
	*스파이 = *스파이 - 2;  // 철수 = 철수 - 2
	printf("스파이가 방문하는 곳 주소: %p, 암호: %d\n", 스파이, *스파이);

	스파이 = &영희;
	*스파이 = *스파이 - 2;  // 영희 = 영희 - 2
	printf("스파이가 방문하는 곳 주소: %p, 암호: %d\n", 스파이, *스파이);

	스파이 = &민수;
	*스파이 = *스파이 - 2;  // 민수 = 민수 - 2
	printf("스파이가 방문하는 곳 주소: %p, 암호: %d\n", 스파이, *스파이);

	// 철수, 영희, 민수는 집에 돌아와서 바뀐 암호를 보고 깜짝 놀람.
	// - 철수 제외!
	printf("철수네 주소: %p, 암호: %d\n", &철수, 철수);
	printf("영희네 주소: %p, 암호: %d\n", &영희, 영희);
	printf("민수네 주소: %p, 암호: %d\n", &민수, 민수);

	// 참고: 미션맨/포인터가 사는 곳의 주소 또한 &미션맨/&스파이 등으로 확인
	printf("미션맨의 주소: %p\n", &미션맨);
	printf("스파이의 주소: %p\n", &스파이);
```

---

### Python 구현


```python

```

---

## (C 언어) 배열과 포인터의 관계

* 동영상: [(나도코딩 C) 7-5 배열과 포인터의 관계](https://www.youtube.com/watch?v=MizWzX-mKfg&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=48)

* 배열을 가리키는 변수는 포인터 변수로 인식됨
* 아래 예제 코드에서 `arr`과 `ptr`은 동일한 배열을 가리킴.

---
```c
#include <stdio.h>

int main()
{
	// 배열

	int arr[3] = {5, 10, 15};
	int * ptr = arr;
	
	// 배열의 항목 확인
	for (int i = 0; i < 3; i++)
	{
		printf("배열 arr[%d]의 값: %d\n", i, arr[i]);
	}

	// 포인터로도 배열 항목 확인 가능
	for (int i = 0; i < 3; i++)
	{
		printf("포인터 ptr[%d]의 값: %d\n", i, ptr[i]);
	}

	// 포인터를 활용하여 배열 항목 수정
	ptr[0] = 100;
	ptr[1] = 200;
	ptr[2] = 300;

	// 배열 항목 다시 확인
	for (int i = 0; i < 3; i++)
	{
		printf("배열 arr[%d]의 값: %d\n", i, arr[i]);
	}

	for (int i = 0; i < 3; i++)
	{
		printf("포인터 ptr[%d]의 값: %d\n", i, ptr[i]);
	}
}
```

* 배열이 저장된 주소를 가리키는 포인터 변수는 실제로는 배열의 첫째 항목이 가리키는 메모리 주소를 가리킴.

<div align="center"><img src="./images/nado07-c-pointer-3.png" width="400"/></div>

<그림 참조: [SessionK 블로그: 배열 포인터연산](https://sessionk.tistory.com/156)>

---
```c
	// 포인터 값을 이용하여 아래와 같이 수정해도 동일하게 작동함
	// 포인터 변수는 어레이의 첫째 항목이 저장된 주소를 가리킴
	for (int i = 0; i < 3; i++)
	{
		printf("배열 arr[%d]의 값: %d\n", i, *(arr + i));
	}

	for (int i = 0; i < 3; i++)
	{
		printf("포인터 ptr[%d]의 값: %d\n", i, *(ptr + i));
	}

	// *(arr + i) == arr[i] 
	// arr == arr 배열의 첫번째 값의 주소와 동일, 즉, &arr[0]
	printf("arr 자체의 값: %p\n", arr);
	printf("arr[0]의 주소: %p\n", &arr[0]);

	// 배열 포인터 주소에 저장된 값 = 배열의 첫째 항목
	printf("arr 자체의 값이 가지는 주소의 실제 값: %d\n", *arr); // *(arr + 0)
	printf("arr[0]의 값: %d\n", *&arr[0]);

	// *& 는 아무 것도 없는 것과 같다. 
	// & 는 주소, * 는 그 주소에 저장된 값
	printf("arr[0]의 값: %d\n", *&*&*&arr[0]);
	printf("arr[0]의 값: %d\n", arr[0]);
```

---

### Python 구현


```python

```

---

## (C 언어) Swap

* 동영상: [(나도코딩 C) 7-6 Swap](https://www.youtube.com/watch?v=CchtxFktL4k&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=49)

### 두 개의 변수에 할당된 값 바꾸기 잘못된 시도

* 아래와 같이 시도하면 변수 a와 b에 저장된 값을 바꿀 수 없음.
* 이유는 swap 함수에 전달되는 것은 a와 b의 주소가 아니라 a와 b가 가리키는 값만 전달되기 때문임.

---
```c
#include <stdio.h>

// 스왑 함수
void swap(int a, int b);

int main()
{
	// Swap

	int a = 10;
	int b = 20;

	// a와 b의 값 바꾸기
	printf("Swap 함수 적용 전 => a: %d, b:%d\n", a, b);
	swap(a, b);
	printf("Swap 함수 적용 후 => a: %d, b:%d\n", a, b);
}

void swap(int a, int b)
{
	int temp = a;
	a = b;
	b = temp;
	printf("Swap 함수 내 => a: %d, b:%d\n", a, b);
}
```

* 실제로 swap 함수 본체 내에서 사용되는 변수들이 가리키는 주소가 다름.

---
```c
#include <stdio.h>

// 스왑 함수
void swap(int a, int b);

int main()
{
	// Swap

	int a = 10;
	int b = 20;
	printf("a의 주소: %p\n", &a);
	printf("b의 주소: %p\n", &b);

	// a와 b의 값 바꾸기
	printf("Swap 함수 적용 전 => a: %d, b:%d\n", a, b);
    // 값에 의한 복사(Call by Value): 값만 복사한다는 의미
	swap(a, b);
	printf("Swap 함수 적용 후 => a: %d, b:%d\n", a, b);
}

void swap(int a, int b)
{
	printf("(swap 함수 본체) a의 주소: %p\n", &a);
	printf("(swap 함수 본체) b의 주소: %p\n", &b);

	int temp = a;
	a = b;
	b = temp;
	printf("Swap 함수 내 => a: %d, b:%d\n", a, b);
}
```

* 위 코드 실행결과

```c
a의 주소: 0x7ffc1b55074c
b의 주소: 0x7ffc1b550748
Swap 함수 적용 전 => a: 10, b:20
(swap 함수 본체) a의 주소: 0x7ffc1b55071c
(swap 함수 본체) b의 주소: 0x7ffc1b550718
Swap 함수 내 => a: 20, b:10
Swap 함수 적용 후 => a: 10, b:20
```

### 두 개의 변수에 할당된 값 바꾸기: 주소값(포인터) 활용

* 스왑 함수에 변수들의 주소를 전달하면 됨.
* 이를 위해 포인터 주소를 인자로 받는 스왑함수 활용

---
```c
#include <stdio.h>

// 스왑 함수
void swap_addr(int * a, int * b);

int main()
{
	// Swap

	int a = 10;
	int b = 20;

	// a와 b의 값 바꾸기
	printf("Swap 함수 적용 전 => a: %d, b:%d\n", a, b);
	// 주소값 전달하는 방식으로
	swap_addr(&a, &b);
	printf("Swap 함수 적용 후 => a: %d, b:%d\n", a, b);
}

void swap_addr(int * a, int * b)
{
	int temp = *a;
	*a = *b;
	*b = temp;
}
```

---

### Python 구현


```python

```

---

## (C 언어) 포인터로 배열 값 변경하기

* 동영상: [(나도코딩 C) 7-7 포인터로 배열 값 변경하기](https://www.youtube.com/watch?v=jYbFtxbWAzA&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=50)

* 배열의 항목을 포인터를 이용하여 수정 가능

---
```c
#include <stdio.h>

// 스왑 함수
void changeArray(int * ptr);

int main()
{
	// 배열의 2번 인덱스 값 변경하기

	int arr2[3] = {10, 20, 30};
	changeArray(arr2);

	for (int i = 0; i < 3; i++)
	{
		printf("%d\n", arr2[i]);
	}
}

void changeArray(int * ptr)
{
	ptr[2] = 50;
}
```

* `changeArray(arr2);`를 `changeArray(&arr2[0]);`로 변경 가능
* 이제 scanf 함수에서 정수를 입력받을 때 `&num` 과 같이 앰퍼샌드 기호(`&`) 사용하는 이유를 이해할 수 있음.

---

### Python 구현


```python

```

---
