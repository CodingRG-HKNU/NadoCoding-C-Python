# 3장 반복문

## (C 언어) 피라미드를 쌓아라

* 동영상: [(나도코딩 C) 3-1 피라미드를 쌓아라](https://www.youtube.com/watch?v=5Xx6tK6HWGs&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=12)

### 반복문 종류

* `for`
* `while`
* `do while`

## (C 언어) 뿔뿔증감연산

* 동영상: [(나도코딩 C) 3-2 불뿔증감연산](https://www.youtube.com/watch?v=9n0nv27dxcs&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=13)

```c
#include <stdio.h>

int main(void) {
	// printf("Hello World\n");

	// ++ 뿔뿔
	int a = 10;
	printf("a는 %d\n", a);

	a++;
	printf("a는 %d\n", a);

	printf("===\n");

	int b = 20;

	// 먼저 더하기 1을 한 다음에 명령문 실행
	// b = b + 1
	printf("b는 %d\n", ++b);

	//  먼저 명령문을 수행한 다음에 명령문 실행
	printf("b는 %d\n", b++);
	// b = b + 1

	printf("===\n");

	int i = 1;
	printf("Hello World %d\n", i++);  // i = 1
	printf("Hello World %d\n", i++);  // i = 2
	printf("Hello World %d\n", i++);  // i = 3
	printf("Hello World %d\n", i++);  // i = 4
	printf("Hello World %d\n", i++);  // i = 5
	printf("Hello World %d\n", i++);  // i = 6
	printf("Hello World %d\n", i++);  // i = 7
	printf("Hello World %d\n", i++);  // i = 8
	printf("Hello World %d\n", i++);  // i = 9
	printf("Hello World %d\n", i++);  // i = 10

	printf("i는 %d\n", i);            // i = 11

	printf("\n===\n\n");

	printf("Hello World %d\n", i--);  // i = 11
	printf("Hello World %d\n", i--);  // i = 10
	printf("Hello World %d\n", i--);  // i = 9
	printf("Hello World %d\n", i--);  // i = 8
	printf("Hello World %d\n", i--);  // i = 7
	printf("Hello World %d\n", i--);  // i = 6
	printf("Hello World %d\n", i--);  // i = 5
	printf("Hello World %d\n", i--);  // i = 4
	printf("Hello World %d\n", i--);  // i = 3
	printf("Hello World %d\n", i--);  // i = 2
	printf("Hello World %d\n", i--);  // i = 1

	printf("i는 %d\n", i);            // i = 0

    return 0;
}
```

#### 주의사항

* ++ 연산 사용은 추천하지 않음.
    * 사유: 복잡한 코드에서 사용하는 경우 계산 순서에 대한 이해를 어렵게 만들 수 있음.
* 또한 파이썬에서는 아예 지원되지 않음.

---

### Python 구현

* `++` 연산 지원하지 않음.

---

## (C 언어) `for`

* 동영상: [(나도코딩 C) 3-3 for](https://www.youtube.com/watch?v=XhoKhevLtmk&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=14)

* `for` 반복문 형식

    ```c
    for (선언;  조건;  증감)
    {
    명령문
    }
    ```

```c
#include <stdio.h>

int main(void) {
	// for 반복문
    
	// 예제: 증가
	for (int i = 1; i <= 10; i++)
	{
		printf("Hello World %d\n", i);
	}

	printf("\n===\n\n");

	// 예제: 감소
	for (int i = 10; i >= 0; i--)
	{
		printf("Hello World %d\n", i);
	}

    return 0;
}
```

---

### Python 구현

* 파이썬의 `for` 반복문은 형식이 많이 다름:

    ```python
    for 반복변수 in 이터레이터:
        명령문
    ```
    
* 이터레이터: 반복변수의 값이 지정된 크기만큼씩 변할 수있도록 도와주는 기능을 가진 자료형
    * 리스트, `range`, 튜플, 사전 자료형 등등
    
* 반복변수는 미리 선언할 필요 없음.

* `for` 반복문과 `range` 함수의 조합이 매우 유용함

#### 증가 예제


```python
for i in range(1, 11):
    print("Hello World %d" % i)
```


```python
for i in [1, 3, 5, 7, 9]:
    print("Hello World %d" % i)
```


```python
for i in range(1, 11, 2):
    print("Hello World %d" % i)
```

#### 감소 예제


```python
for i in range(10, 0, -1):
    print("Hello World %d" % i)
```


```python
for i in range(10, 0, -2):
    print("Hello World %d" % i)
```

---

## (C 언어) `while`

* 동영상: [(나도코딩 C) 3-4 while](https://www.youtube.com/watch?v=Um-61He4Lhw&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=15)

* `while` 반복문 형식

    ```c
    while (조건)
    {
    명령문
    }
    ```

```c
 #include <stdio.h>

int main(void) {
	// while 반복문

	int i = 1;
	while (i <= 10)
	{
		// printf("Hello World %d\n", i);
		// i++;
		printf("Hello World %d\n", i++);
	}

    return 0;
}
```

---

### Python 구현

* 파이썬의 `while` 반복문 형식은 C 언어의 경우와 거의 동일함.


```python
i = 1

while (i <= 10):
    print("Hello World %d" % i)
    i += 1
```


```python
i = 1

while (i <= 10):
    print("Hello World %d" % i)
    i += 2
```

* 파이썬의 `print()` 함수는 다양한 자료형의 인자 여러 개를 받을 수 있음.
* 따라서 아래와 같이 포맷팅 문자열을 굳이 사용하지 않아도 됨.


```python
i = 1

while (i <= 10):
    print("Hello World", i)
    i += 2
```

---

## (C 언어) `do while`

* 동영상: [(나도코딩 C) 3-5 do while](https://www.youtube.com/watch?v=4eDDQU9Mwic&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=16)

* `do while` 반복문 형식

    ```c
    do 
    {
    명령문
    } while (조건);
    ```

```c
#include <stdio.h>

int main(void) {
	// do while 반복문

	int i = 1;
	do
	{
		printf("Hello World %d\n", i++);
	} while (i <= 10);

    return 0;
}```

#### 주의사항

* `do while` 반복문의 사용 가능하면 사용하지 말 것.
* `while` 반복문을 이용하여 동일한 기능 구현 가능.
* 파이썬 등 일부 언어에서 지원되지 않음.

---

### Python 구현

* `do while` 지원하지 않음.

---

## (C 언어) 이중 반복문(구구단)

* 동영상: [(나도코딩 C) 3-6 이중 반복문(구구단)](https://www.youtube.com/watch?v=P448GE1UGbQ&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=17)

* `for` 반복문 중첩해서 사용하기

```c
#include <stdio.h>

int main(void) {
	// 2중 반복문

	for (int i = 1; i <= 3; i++)
	{
		printf("첫재 반복문: %d\n", i);

			for (int j = 1; j <= 5; j++)
				{
					printf("    둘째 반복문: %d\n", j);
				}
	}

    return 0;
}
```

* 구구단 구현하기

```c
#include <stdio.h>

int main(void) {
	// 구구단

	for (int i = 2; i <= 9; i++)
	{
        printf("%d단:\n", i);
		
		for (int j = 1; j <= 9; j++)
		{
			printf("    %d x %d = %d\n", i, j, i*j);
		}
	}
    
    return 0;

} 
```

---

### Python 구현

* 이중 반복문 구조는 사용하는 프로그래밍언와 상관 없이 모두 동일한 형식을 가짐.
* 파이썬 `for` 반복문으로 구구단 구현하기 예제는 다음과 같음.
* 아래 코드에서 사용되는 `f"..."`은 문자열을 지정된 서식에 맞추어 출력되도록 도와주는 기법임
    * 문자열 서식지원 기법 중에서 가장 사용하기 편리한 기능임.
    * f-문자열 포매팅이라 불림.
    * 사용법 참조:[점프투파이썬: f-문자열 포매팅](https://wikidocs.net/13#f) 


```python
for i in range(2, 10):
    print(f"{i}단")
    for j in range(1, 10):
        print(f"     {i}x{j}={i*j}")
```

---

## (C 언어) 이중 반복문 파헤치기

* 동영상: [(나도코딩 C) 3-7 이중 반복문 파헤치기](https://www.youtube.com/watch?v=4gV1MjGIL3E&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=18)

* 아래 모양의 별 피라미드 출력하기

```
*
**
***
****
*****
```

```c
#include <stdio.h>

int main(void) {
    // 별 피라미드 출력하기
    
	for (int i = 0; i<5; i++)
	{
		for (int j = 0; j <= i; j++)
		{
			printf("*");
		}
		printf("\n");
	}

    return 0;

} 
```

#### PythonTutor 활용하기

* [(C 언어) 별 피라미드 그리기](http://www.pythontutor.com/visualize.html#code=%23include%20%3Cstdio.h%3E%0A%0Aint%20main%28void%29%20%7B%0A%20%20%20%20//%20%EB%B3%84%20%ED%94%BC%EB%9D%BC%EB%AF%B8%EB%93%9C%20%EC%B6%9C%EB%A0%A5%ED%95%98%EA%B8%B0%0A%20%20%20%20%0A%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%3C5%3B%20i%2B%2B%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20j%20%3D%200%3B%20j%20%3C%3D%20i%3B%20j%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22*%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20printf%28%22%5Cn%22%29%3B%0A%20%20%20%20%7D%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)

---

### Python 구현

* 별 피라미드 구하기
* C 언어 프로그램과 동일한 구조를 가짐.
* 주의사항: 파이썬의 `print()` 함수는 줄바꿈(`\n`)을 기본으로 실행함.
    하지만 `end=''`와 같이 옵션인자의 속성을 변경하면 줄바꿈을 해제할 수 있음.


```python
for i in range(0, 5):
    for j in range(0, i+1):
        print("*", end='')     # 동일한 i 값에 대해서는 줄바꿈 해제
    print('')                  # i 값이 바뀔때는 줄바꿈을 해주어야 함.
```

    *
    **
    ***
    ****
    *****


---

## (C 언어) 이중 반복문 거꾸로 별

* 동영상: [(나도코딩 C) 3-8 이중 반복문 거꾸로 별](https://www.youtube.com/watch?v=jjIgIPMwgLA&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=19)

* 아래 모양의 별 피라미드 출력하기

```
    *
   **
  ***
 ****
*****
```

```c
#include <stdio.h>

int main(void) {
    for (int i = 0; i<5; i++)
	{
		for (int j = i; j < 5-1; j++)
        {
            // 스페이스 추가
			printf(" ");
		}

		for (int k = 0; k <= i; k++)
		{
			printf("*");
		}
		printf("\n");
	}

    return 0;

} 
```

#### PythonTutor 활용하기

* [(C 언어) 거꾸로 별 그리기](http://pythontutor.com/visualize.html#code=%23include%20%3Cstdio.h%3E%0A%0Aint%20main%28void%29%20%7B%0A%20%20%20%20/*%20%EC%95%84%EB%9E%98%20%EB%AA%A8%EC%96%91%EC%9D%98%20%EB%B3%84%20%EA%B7%B8%EB%A6%AC%EA%B8%B0%0A%20%20%20%20%20%20%20%20*%0A%20%20%20%20%20%20%20**%0A%20%20%20%20%20%20***%0A%20%20%20%20%20****%0A%20%20%20%20*****%0A%20%20%20%20*/%0A%20%20%20%20%0A%20%20%20%20for%20%28int%20i%20%3D%200%3B%20i%3C5%3B%20i%2B%2B%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20j%20%3D%20i%3B%20j%20%3C%205-1%3B%20j%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20//%20%EC%8A%A4%ED%8E%98%EC%9D%B4%EC%8A%A4%20%EC%B6%94%EA%B0%80%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22%20%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%0A%20%20%20%20%20%20%20%20for%20%28int%20k%20%3D%200%3B%20k%20%3C%3D%20i%3B%20k%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22*%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20printf%28%22%5Cn%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20return%200%3B%0A%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)

---

### Python 구현

* 거구로 별 피라미드 구하기
* C 언어 프로그램과 동일한 구조로 구현 가능


```python
for i in range(0, 5):
    for j in range(i, 4):
        # 스페이스 추가
        print(" ", end='')

    for k in range(0, i+1):
        print("*", end='')

    print("")
```

        *
       **
      ***
     ****
    *****


* 하지만 다음과 같이 문자열과 정수의 곱셈을 활용할 수도 있음.
* for 반복문 사용하지 않고 구현 가능.


```python
print("*"*4)
```

    ****



```python
for i in range(0, 5):
    # 스페이스 추가
    print(" "* (4-i), end='')
    # 별 찍기
    print("*" * (i+1), end='')
    # 줄바꿈 
    print("")
```

        *
       **
      ***
     ****
    *****


---

## (C 언어) 프로젝트: 피라미드를 쌓아라

* 동영상: [(나도코딩 C) 3-9 프로젝트: 피라미드를 쌓아라](https://www.youtube.com/watch?v=H8-sbBu0blU&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=20)

* 아래 모양의 별 피라미드 출력하기

```
    	*
	   ***
	  *****
	 *******
	*********
```

```c
#include <stdio.h>

int main(void) {

    int floor;
	printf("몇 층으로 쌓겠느냐? ");
	scanf("%d", &floor);

	for (int i=0; i < floor; i++)
	{
		for (int j = i; j < floor-1; j++)
		{
            // 스페이스 추가
			printf(" ");
		}

		for (int k = 0; k < i*2 + 1; k++)
		{
            printf("*");
		}
		printf("\n");
	}

    return 0;

} 
```

#### PythonTutor 활용하기

* [(C 언어) 프로젝트: 피라미드를 쌓아라](http://pythontutor.com/visualize.html#code=%23include%20%3Cstdio.h%3E%0A%0Aint%20main%28void%29%20%7B%0A%20%20%20%20/*%20%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%3A%20%ED%94%BC%EB%9D%BC%EB%AF%B8%EB%93%9C%EB%A5%BC%20%EC%8C%93%EC%95%84%EB%9D%BC%0A%20%20%20%20%20%20%20%20*%0A%20%20%20%20%20%20%20***%0A%20%20%20%20%20%20*****%0A%20%20%20%20%20*******%0A%20%20%20%20*********%0A%20%20%20%20*/%0A%20%20%20%20%0A%20%20%20%20int%20floor%3B%0A%20%20%20%20printf%28%22%EB%AA%87%20%EC%B8%B5%EC%9C%BC%EB%A1%9C%20%EC%8C%93%EA%B2%A0%EB%8A%90%EB%83%90%3F%5Cn%22%29%3B%0A%20%20%20%20//%20PythonTutor%EC%97%90%EC%84%9C%20scanf%20%EC%A7%80%EC%9B%90%ED%95%98%EC%A7%80%20%EC%95%8A%EC%9D%8C%0A%20%20%20%20//%20%EB%94%B0%EB%9D%BC%EC%84%9C%205%EC%B8%B5%EC%9C%BC%EB%A1%9C%20%EC%A7%80%EC%A0%95%0A%20%20%20%20//%20scanf%28%22%25d%22,%20%26floor%29%3B%0A%20%20%20%20floor%20%3D%205%3B%0A%0A%20%20%20%20for%20%28int%20i%3D0%3B%20i%20%3C%20floor%3B%20i%2B%2B%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20j%20%3D%20i%3B%20j%20%3C%20floor-1%3B%20j%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20//%20%EC%8A%A4%ED%8E%98%EC%9D%B4%EC%8A%A4%20%EC%B6%94%EA%B0%80%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22%20%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%0A%20%20%20%20%20%20%20%20for%20%28int%20k%20%3D%200%3B%20k%20%3C%20i*2%20%2B%201%3B%20k%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22*%22%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20printf%28%22%5Cn%22%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20return%200%3B%0A%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)

---

### Python 구현


```python
floor = int(input("몇 층으로 쌓겠느냐? "))

for i in range(0, floor):
    for j in range(i, floor-1):
        # 스페이스 추가
        print(" ", end='')

    for k in range(0, i*2+1):
        print("*",end='')

    print("")
```

    몇 층으로 쌓겠느냐? 5
        *
       ***
      *****
     *******
    *********


* 이전에 설명한 것처럼 문자열과 정수의 곱셈을 이용하면 for 반복문 사용하지 않고 구현 가능. 


```python
floor = int(input("몇 층으로 쌓겠느냐? "))

for i in range(0, floor):
    # 스페이스 추가
    print(" "* (floor-i), end='')
    # 별 찍기
    print("*" * (i*2+1), end='')
    # 줄바꿈 
    print("")
```

    몇 층으로 쌓겠느냐? 5
         *
        ***
       *****
      *******
     *********


---
