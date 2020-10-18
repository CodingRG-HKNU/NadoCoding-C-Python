# 6장 배열

## 핵심

* 배열 개념 및 정의
* 문자열 활용

## (C 언어) 아빠는 대머리

* 동영상: [(나도코딩 C) 6-1 아빠는 대머리](https://www.youtube.com/watch?v=5VIDqDdKDsw&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=37&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9)

### 게임 설명

* 발모제의 조합을 테스트하면서 효과있는 발모제 찾기

---

## (C 언어) 배열 기초

* 동영상: [(나도코딩 C) 6-2 계산기](https://www.youtube.com/watch?v=pr0r_dZht0g&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=38&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9)

* 여러 개의 값을 여러 개의 변수에 저장해서 활용할 수 있지만 비효율적임.

---
```c
#include <stdio.h>
 
int main()
{
    // 배열
    int subway_1 = 30; // 지하철 1호차에 30명이 타고 있다.
    int subway_2 = 40; // 지하철 1호차에 40명이 타고 있다.
    int subway_3 = 50; // 지하철 1호차에 50명이 타고 있다.

    printf("지하철 1호차에 %d 명이 타고 있습니다.\n", subway_1);
    printf("지하철 2호차에 %d 명이 타고 있습니다.\n", subway_2);
    printf("지하철 3호차에 %d 명이 타고 있습니다.\n", subway_3);

    return 0;
}
```

* 여러 개의 값을 하나의 어레이에 저장하여 동시에 활용할 수 있음.
* 인덱스가 0부터 시작함에 주의할 것.

---
```c
#include <stdio.h>
 
int main()
{
    // 여러 개의 변수를 함께, 동시에 생성
    int subway_array[3];
    
    subway_array[0] = 30;
    subway_array[1] = 40;
    subway_array[2] = 50;
    
    for (int i = 0; i < 3; i++)
    {
        printf("지하철 %d호차에 %d 명이 타고 있습니다.\n", i+1, subway_array[i]);
    }

    return 0;
}
```

---

### Python 구현

* 아래 두 함수를 잘 활용해야 함.

* `len()`: 리스트의 길이 반환


```python
len([1, 3, 5, 7])
```




    4



* `range()`: 인자로 사용된 양의 정수까지의 리스트와 비슷한 값 반환


```python
range(5)
```




    range(0, 5)



* `range(5)`는 `[0, 1, 2, 3, 4]`와 비슷한 성질의 가짐. 
* 주의: 하지만 리스트와 자료형은 다름.
* 그래도 `for` 반복문과 함께 사용될 수 있음.


```python
for i in range(5):
    print(i)
```

    0
    1
    2
    3
    4


* 이제 `len()`과 `range()` 함수를 활용하여 위 C 코드를 파이썬에서 동일하게 구현 가능.


```python
# 리스트: 여러 개의 값을 동시에 저장하는 기능

# 길이가 3인 리스를 선언한 후에 나중에 항목을 업데이트 하고자 할 경우 
# 먼저 리스트 항목을 임의의 값으로 초기화 해야 함.
subway_array = [0, 0, 0]

# 인덱싱을 이용한 항목 업데이트는 C 언어의 경우와 동일하게 진행
subway_array[0] = 30
subway_array[1] = 40
subway_array[2] = 50

# 리스트와 for 문은 매우 잘 어울림.
# C 언어의 for 문과 형식이 많이 다름.
for i in range(len(subway_array)):
    print(f"지하철 {i+1}호차에 {subway_array[i]} 명이 타고 있습니다.")
```

    지하철 1호차에 30 명이 타고 있습니다.
    지하철 2호차에 40 명이 타고 있습니다.
    지하철 3호차에 50 명이 타고 있습니다.


---

## (C 언어) 어레이 항목 값 설정

* 동영상: [(나도코딩 C) 6-3 값 설정](https://www.youtube.com/watch?v=6B-Vu7Ox7zQ&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=39&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9)

* 어레이를 선언할 때 항목값을 함께 설정 가능

---
```c
#include <stdio.h>
 
int main()
{
    // 어레이 항목값 설정 방법

	int arr[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}; 

	for (int i=0; i<10; i++)
	{
		printf("%d\n", arr[i]);
	}

    return 0;
}
```

* 하지만 어레이를 선언만 하면 항목값이 임의로 초기화됨에 주의할 것.

---
```c
#include <stdio.h>
 
int main()
{
    // 어레이 항목값 설정 방법

	int arr[10];
    
    // 아래 코드를 실행하면 엉뚱한 값들이 확인됨.

	for (int i=0; i<10; i++)
	{
		printf("%d\n", arr[i]);
	}

    return 0;
}
```

* 아래와 같이 소위 더미(dummy)값이라는 쓰레기값이 임의로 지정됨에 주의할 것.
    * 시스템마다 다를 수 있음.
    * 따라서 항상 함께 항목값을 직접 지정한 후에 사용해야 함.

```c
742975984
32572
0
0
4196848
0
4195712
0
-594061760
32764
```

* 어레이의 길이에 변수 사용 불가
    * 즉, 배열의 크기는 항상 상수로 선언해야 함.

```c
// 배열 크기는 항상 상수로 선언해야 함.
/* 아래 코드 사용 불가
int size =10;
int arr[size];
*/

int arr[10];
```

* 어레이 크기보다 적은 수의 항목만을 입력하면 나머지 항목의 값은 0으로 지정됨.

---
```c
#include <stdio.h>
 
int main()
{
    // 어레이 항목값 설정 방법

	int arr[10] = {1, 2}; // 셋째 값부터는 모두 0으로 지정됨.
    
    // 아래 코드를 실행하면 엉뚱한 값들이 확인됨.

	for (int i=0; i<10; i++)
	{
		printf("%d\n", arr[i]);
	}

    return 0;
}
```

* 처음 두 개의 항목을 제외한 나머지 항목은 모두 0으로 초기화됨.

```c
1
2
0
0
0
0
0
0
0
0
```

* 부동소수점의 경우는 0.0으로 초기화됨.

```c
#include <stdio.h>
 
int main()
{
    // 어레이 항목값 설정 방법

	float arr_f[5]={1.0f, 2.0f, 3.0f}; 

	for (int i=0; i<5; i++)
	{
		printf("%.2f\n", arr_f[i]);
	}

    return 0;
}
```

```c
1.00
2.00
3.00
0.00
0.00
```

* 어레이 크기 미지정 선언 가능

```c
int arr[] = {1, 2} // arr[2]와 동일한 의미임
```

---

### Python 구현

* 파이썬에서 리스트의 항목과 개수는 항상 직접 지정해야 함.

* for 반복문을 위해 `len()`과 `range()` 함수 활용


```python
# 어레이 항목값 설정 방법

arr = [1, 3, 5, 7, 9]

# len()과 range() 활용
for i in range(len(arr)):
    print(arr[i])
```

    1
    3
    5
    7
    9


* 하지만 리스트의 항목을 직접 가리킬 수도 있음.


```python
# 어레이 항목값 설정 방법

arr = [1, 3, 5, 7, 9]

# 항목 직접 사용
for item in arr:
    print(item)
```

    1
    3
    5
    7
    9


---

## (C 언어) 문자와 문자열

* 동영상: [(나도코딩 C) 6-4 문자 vs 문자열](https://www.youtube.com/watch?v=CXi3CykWah8&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=40&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9)

* 문자와 문자열을 구분하여 사용
* `char`: 문자 자료형. 하나의 문자만 포함. 작은 인용부호 사용.
* 문자열: 
    * 문자로 이루어진 배열로 처리. 
    * 즉, 문자열 자료형이 따로 존재하지 않음.
    * 배열의 길이는 사용하는 문자열의 크기보다 1크게 선언해야 함.

---
```c
#include <stdio.h>

// 문자 vs 문자열 

int main()
{
	// 문자
	char c = 'A';
	printf("%c\n", c);

	// 문자열 끝을 의미하는 NULL 문자인 '\0'이 반드시 포함되어야 함.
	// 즉, 지정된 문자열의 크기보다 1크게 선언해야 함.
	// char str[6] = "coding"; 
	char str[7] = "coding"; 
	printf("%s\n", str);

	// 일반적으로 문자열의 길이를 지정하지 않게 선언함.
	char str1[] = "coding";
	printf("%s\n", str1);

	// 문자열의 크기에 1이 더해짐에 주의할 것
	// 문자열의 크기는 unsigned long 자료형을 갖는 정수값임.
	printf("%d\n", sizeof(str1));

    return 0;
}
```

#### 문자열과 for 반복문

* for 반복문과 인덱싱을 이용하여 문자열 항목 확인 가능.

```c
#include <stdio.h>

// 문자 vs 문자열 

int main()
{
	char str[] = "coding";

	for(int i=0; i<sizeof(str); i++)
	{
		printf("%c\n", str[i]);
	}

    return 0;
}
```

* 주의: 마지막에 NULL 문자 또한 출력됨.

```c
c
o
d
i
n
g
   (<== 빈칸이 이곳에 보여짐)
```

#### 한글 문자열 활용

* 한글의 글자는 시스템에 따라 2-3 바이트 사용함.
* 반면에 영어 알파벳은 1 바이트 활용

```c
#include <stdio.h>

// 문자 vs 문자열 

int main()
{
	char kor[] = "나도코딩";
	printf("%s\n", kor);
	printf("%lu\n", sizeof(kor));
	// 영어 1글자: 1 byte
	// 한글 1글자: 2-3 byte
	// char 크기: 1 byte
    return 0;
}
```

* 문자열 "나도코딩"의 크기는 $13 = 3 \cdot 4 + 1$

```c
나도코딩
13
```

---

### Python 구현

* 문자 자료형이 따로 없음.
* 대신에 문자는 길이가 1인 문자열에 불과함.
* 작은따옴표와 큰따옴표는 동일한 기능 수행


```python
# 문자 vs 문자열 

# 문자
c = 'A'
print(c)

# 문자열의 자료형은 str
string = "coding" 
print(type(string))

# 문자열의 길이는 사용된 문자의 수. 
# C 언어와는 달리 Null 문자 고려하지 않음.
print(len(string))

# 한글의 경우 문자열의 길이는 글자 수임.
print(len("나도코딩"))
```

    A
    <class 'str'>
    6
    4


* 바이트 단위의 크기를 알고 싶을 때는 `sys` 모듈의 `getsizeof()` 함수 활용 가능
    * 문자열 자료형의 `__sizeof__()` 메서드 호출함.
    * 가비지컬렉션에 사용할 메모리 크기까지 포함하기에 별 의미 찾기 어려움.
    * 따라서 굳이 사용할 필요 없음.


```python
from sys import getsizeof
```


```python
getsizeof("나도코딩")
```




    82




```python
getsizeof("coding")
```




    55



---

## (C 언어) 문자열 심화

* 동영상: [(나도코딩 C) 6-5 문자열 심화](https://www.youtube.com/watch?v=MxUudXTn-2E&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=41)

* 문자열을 문자로 구성된 배열로 동일하게 구현 가능.

---
```c
#include <stdio.h>

// 문자열 심화

int main()
{
	char arr[7] = "coding";
	// 위 문자열의 원래 정의는 다음과 같음.
	// 끝에 문자열의 끝을 알려주는 널 문자를 포함하는 것에 주의할 것.
	char c_array[7] = {'c', 'o', 'd', 'i', 'n', 'g', '\0'};

	printf("%s\n", arr);
	printf("%s\n", c_array);

    return 0;
}
```

#### 널문자와 배열의 크기

* 배열의 크기를 충분히 크게 하면 남은 공간은 널문자로 대체됨.

```c
#include <stdio.h>

// 문자열 심화

int main()
{
	// 배열의 길이를 사용된 문자열의 크기보다 크게 지정한 경우
	char c_array[10] = {'c', 'o', 'd', 'i', 'n', 'g'};

	// 마지막에 널 문자를 명시하지 않더라도 문자열 출력에 전혀 문제 없음.
	// 널 문자가 자동으로 삽입되며, 남은 공간도 동일하게 취급됨.
	// 이 점을 for 반복문으로 직접 확인 가능.

	for (int i=0; i < sizeof(c_array); i++)
	{
		printf("%c\n", c_array[i]);
	}

    return 0;
}
```

```c
c
o
d
i
n
g




```

#### 문자와 아스키(ascii) 코드

* 아스키 코드: 사용되는 문자와 숫자 사이의 연관관계

```c
#include <stdio.h>

// 문자와 아스키 코드

int main()
{
	// 배열의 길이를 사용된 문자열의 크기보다 크게 지정한 경우
    char c_array[10] = {'c', 'o', 'd', 'i', 'n', 'g'};

	// 각각의 문자에 아스키(ascii) 코드라는 숫자가 대응됨.
	// 이 점을 for 반복문으로 직접 확인 가능.

	for (int i=0; i < sizeof(c_array); i++)
	{
		printf("%d\n", c_array[i]);    // %d 사용에 주의
	}

    return 0;
}
```

```c
99
111
100
105
110
103
0
0
0
0
```

#### 널 문자 다음에 오는 문자

* 널 문자 다음에 오는 문자들은 모두 무시됨. 널 문자가 문자열의 끝으로 인식되기 때문.

```c
#include <stdio.h>

// 문자와 아스키 코드

int main()
{
	// 배열의 길이를 사용된 문자열의 크기보다 크게 지정한 경우
    char c_array[10] = {'c', 'o', 'd', 'i', 'n', 'g', '\0', 'c' };

	// 문자열 전체를 한꺼번에 출력하면 널문자는 무시됨.
	printf("%s\n", c_array);    // %d 사용에 주의

    return 0;
}
```

```c
coding
```

---

### Python 구현

* 파이썬에서 문자는 길이가 1인 문자열로 처리함. 따라서 `char`에 해당하는 자료형 없음.
* 또한 널문자(`\0`)와 동일한 기능의 문자도 없음. 물론 널문자를 가리키는 문자열 `\0`은 사용 가능.


```python
print('\0')
```

     


* 빈문자열과 동일함.


```python
print('')
```

    


---

## (C 언어) 아스키 코드

* 동영상: [(나도코딩 C) 6-6 아스키 코드](https://www.youtube.com/watch?v=-brVtblamCY&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=42)

* ANSI(미국표준협회)에서 제시한 표준코드 체계
* 7 bit 크기로 표현할 수 있는 문자 표준체계
* 총 $128 ( = 2^7$)개의 문자 표현 가능

---
```c
#include <stdio.h>

// 아스키 코드

int main()
{
	// 소문자 a, b, c 는 97, 98, 99 등으로 시작
    printf("%c는 아스키 코드로 %d\n", 'a', 'a');
    printf("%c는 아스키 코드로 %d\n", 'b', 'b');
    printf("%c는 아스키 코드로 %d\n", 'c', 'c');

	// 대문자 A, B, C 는 65, 66, 67 등으로 시작
    printf("%c는 아스키 코드로 %d\n", 'A', 'A');
    printf("%c는 아스키 코드로 %d\n", 'B', 'B');
    printf("%c는 아스키 코드로 %d\n", 'C', 'C');

	// 널문자 `\0`은 아스키 코드 0임.
    printf("널문자 %c는 아스키 코드로 %d\n", '\0', '\0');

	// 숫자 0, 1, 2 는 48, 49, 50 등으로 시작
    printf("%c는 아스키 코드로 %d\n", '0', '0');
    printf("%c는 아스키 코드로 %d\n", '1', '1');
    printf("%c는 아스키 코드로 %d\n", '2', '2');

    return 0;
}
```

```c
a는 아스키 코드로 97
b는 아스키 코드로 98
c는 아스키 코드로 99
A는 아스키 코드로 65
B는 아스키 코드로 66
C는 아스키 코드로 67
널문자 는 아스키 코드로 0
0는 아스키 코드로 48
1는 아스키 코드로 49
2는 아스키 코드로 50
```

#### 아스키 코드 전체

* 전체 아스키 코드와 간단한 역사는
    [위키피디아: 아스키 코드](https://ko.wikipedia.org/wiki/ASCII)
    에서 확인 가능.

---

### Python 구현

#### 파이썬과 아스키 코드

* 아스키 코드 문자 사이의 대응관계는 C 언어의 경우와 동일함. 

* 하지만 관계를 확인하려면 `ord()` 함수와 `chr()` 함수를 활용해야 함.

* `ord()` 함수: 문자를 아스키 코드 숫자로 변환


```python
for item in ['a', 'b', 'c']:
    print(ord(item))
```

    97
    98
    99



```python
for item in ['A', 'B', 'C']:
    print(ord(item))
```

    65
    66
    67



```python
for item in ['0', '1', '2']:
    print(ord(item))
```

    48
    49
    50


* 널문자의 아스키 코드 번호는 0.


```python
print(ord('\0'))
```

    0


* `chr()` 함수는 아스키 코드를 해당 문자로 변환함.


```python
for num in range(97, 100):
    print(chr(num))
```

    a
    b
    c



```python
for num in range(65, 68):
    print(chr(num))
```

    A
    B
    C



```python
for num in range(48,51):
    print(chr(num))
```

    0
    1
    2


* 널문자 표기


```python
chr(0)
```




    '\x00'



#### 유니코드

* `chr()`과 `ord()` 함수는 실제로는 아스키 코드를 확장한 유니코드도 지원함.
* 따라서 한글도 지원함.


```python
ord('ㄱ')
```




    12593




```python
ord('썬')
```




    50028




```python
chr(12593)
```




    'ㄱ'




```python
chr(50028)
```




    '썬'



* 아스키코드, 유니코드, utf8 등에 대한 간단한 설명은 
    [초보몽키: 강의노트 06. ASCII, UNICODE, utf8](https://wayhome25.github.io/cs/2017/04/05/cs-06/) 참조

---

## (C 언어) 프로젝트

* 동영상: [(나도코딩 C) 6-7 프로젝트](https://www.youtube.com/watch?v=W1b7YhFjc70&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=43)

* 아빠는 대머리 게임: 발모제 찾기 게임

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// 아빠는 대머리 게임: 발모제 찾기

int main()
{
	srand(time(NULL));
	
	printf("\n\n === 아빠는 대머리 게임 === \n\n");

	int answer; // 사용자 입력값
	int treatment = rand() % 4; // 네 개의 발모제 중 산택 (0 - 3)

	// 무작위로 보여줄 병 개수 지정. 
	// 정답률을 향상시키기 위해 병의 수를 2개 또는 3개로 번갈아 가면서 지정

	int cntShowBottle = 0; // 이번 게임에 보여줄 병 개수
	int prevCntShowBottle = 0; // 앞 게임에 보여준 병 개수

    // 게임 세팅하기
    
	// 발모제에 대한 정보를 3번 전달함.

	for (int i=1; i <= 3; i++)
	{
        // 보여줄 병의 개수를 2개 또는 3개로 번갈아 임의로 선택
		int bottle[4] = {0, 0, 0, 0}; // 병 4개
		do {
			cntShowBottle = rand() % 2 + 2; // 보여줄 병 개수는 2-3개
		} while (cntShowBottle == prevCntShowBottle); 

		prevCntShowBottle = cntShowBottle;

        // 선택된 병의 개수만큼 병 선택

        // 발모제 포함여부에 따라 약의 효과여부 전달
		int isincluded = 0;

        // 몇 번째 정보인지 알려줌.
		printf(" > %d 번째 시도: ", i);

		// 보여줄 병 종류 선택
		for (int j = 0; j < cntShowBottle; j++)
		{
			int randBottle = rand() % 4; // 0 - 3

			// 아직 선택되지 않은 병인 경우만 선택
			if (bottle[randBottle] == 0)
			{
				bottle[randBottle] = 1;

				if (randBottle == treatment)
				{
					isincluded = 1;  // 포함된 것 기억
				}
			}
			else  // 이미 선택된 병인 경우 j값을 늘리지 않고 다시 선택하기 위해
			{
				j--;
			}
		}

		// 사용자에게 준비된 3개의 물병조합 보여주기
		for (int k = 0; k < 4; k++)
		{
			if (bottle[k] == 1)
			{
				printf("%d ", k+1); 
			}
		}
		printf(" 물약을 머리에 바릅니다.\n\n");

		if (isincluded == 1)
		{
			printf(" >> 성공 ! 머리가 났어요 !!\n");
		}
		else
		{
			printf(" >> 실패 ! 머리가 나지 않었어요.. ㅠㅠ\n");
		}

		printf("\n ... 계속 하려면 아무 키나 누르세요 ...\n");
		getchar();  //임의의 값을 입력할 때까지 대기하는 용도로 사용
	}

	printf("\n\n 발모제는 몇 번일까요? ");
	scanf("%d", &answer);

	if (answer == treatment + 1)
	{
		printf("\n >> 정답입니다!\n");
	}
	else
	{
		printf("\n >> 땡! 틀렸어요. 정답은 %d 입니다.\n", treatment + 1);
	}
    return 0;
}
```

### 함수 활용하기

* 위와 같이 `main` 함수에 모든 코드를 작성하면 코드의 전체 구조를 살펴보기 매우 어려움.
* 함수를 사용하여 코드의 구조를 명확하게 드러나게 할 수 있음.

#### 예제

* 아래 코드는 게임세팅을 위한 부분을 `game_setting()` 함수로 분리하여 활용함.

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// 아빠는 대머리 게임: 발모제 찾기

// 게임세팅을 위한 함수
void game_setting(int treatment);

int main()
{
	srand(time(NULL));
	
	printf("\n\n === 아빠는 대머리 게임 === \n\n");

	int answer; // 사용자 입력값
	int treatment = rand() % 4; // 네 개의 발모제 중 산택 (0 - 3)

	game_setting(treatment);

	printf("\n\n 발모제는 몇 번일까요? ");
	scanf("%d", &answer);

	if (answer == treatment + 1)
	{
		printf("\n >> 정답입니다!\n");
	}
	else
	{
		printf("\n >> 땡! 틀렸어요. 정답은 %d 입니다.\n", treatment + 1);
	}
    return 0;
}

void game_setting(int treatment)
{
	// 무작위로 보여줄 병 개수 지정. 
	// 정답률을 향상시키기 위해 병의 수를 2개 또는 3개로 번갈아 가면서 지정

	int cntShowBottle = 0; // 이번 게임에 보여줄 병 개수
	int prevCntShowBottle = 0; // 앞 게임에 보여준 병 개수

    // 게임 세팅하기
    
	// 발모제에 대한 정보를 3번 전달함.
	for (int i=1; i <= 3; i++)
	{
        // ***보여줄 병의 개수를 2개 또는 3개로 번갈아 임의로 선택***
        
        // 4개의 물병준비
        // 인덱스에 해당하는 물병의 사용여부 저장
		int bottle[4] = {0, 0, 0, 0}; // 병 4개
		do {
			cntShowBottle = rand() % 2 + 2; // 보여줄 병 개수는 2-3개
		} while (cntShowBottle == prevCntShowBottle); 

		prevCntShowBottle = cntShowBottle;

        // ***선택된 병의 개수만큼 병 선택***

        // 발모제 포함여부에 따라 약의 효과여부 전달
		int isincluded = 0; // 보여줄 병들에 발모제 포함 여부
    
        // 몇 번째 정보인지 알려줌.
		printf(" > %d 번째 시도: ", i);

		// 보여줄 물병 종류 선택
		for (int j = 0; j < cntShowBottle; j++)
		{
			int randBottle = rand() % 4; // 0 - 3

			// 아직 선택되지 않은 물병만 선택
			if (bottle[randBottle] == 0)
			{
				bottle[randBottle] = 1;

				if (randBottle == treatment)
				{
					isincluded = 1;  // 포함된 것 기억
				}
			}
			else  // 이미 선택된 병인 경우 j값을 늘리지 않고 다시 선택하기 위해
			{
				j--;
			}
		}

		// ***사용자에게 준비된 3개의 물병조합 보여주기***
		for (int k = 0; k < 4; k++)
		{
			if (bottle[k] == 1)
			{
				printf("%d ", k+1); 
			}
		}
		printf(" 물약을 머리에 바릅니다.\n\n");

		if (isincluded == 1)
		{
			printf(" >> 성공 ! 머리가 났어요 !!\n");
		}
		else
		{
			printf(" >> 실패 ! 머리가 나지 않었어요.. ㅠㅠ\n");
		}

		printf("\n ... 계속 하려면 아무 키나 누르세요 ...\n");
		getchar();  //임의의 값을 입력할 때까지 대기하는 용도로 사용
	}
}
```

---

### Python 구현

* C 언어 코드를 거의 그대로 변환할 수 있음.

* 주의사항 1: 파이썬은 `do ... while ...` 반복문을 지원하지 않음. 
    * 하지만 아래 형식 사용 가능
    
    ```python
    while True
        명령문
        if not 조건식:
            break
    ```
    
    * 위 파이썬 코드는 아래 C 코드와 동일한 기능 수행
    
    ```c
    do
    {
        명령문
    } while 조건식;
    ```

* 주의사항 2: 파이썬의 `for` 문은 인덱스를 뒤로 돌릴 수 없음에 주의.
    * 그런 기능이 필요할 경우 `while` 반복문 사용할 것.    


```python
import random 
import time

# 현재 시간에 맞추어 무작위로 정수 생성 가능

# time 함수: 1970.01.01 이후 흐른 시간(ns 단위)
current_time = int(time.time())
# 현재 시간 기준으로 무작위수 생성 지정
random.seed(current_time)
```


```python
# 게임세팅을 위한 함수

def game_setting(treatment):
    # 무작위로 보여줄 병 개수 지정. 
    # 정답률을 향상시키기 위해 병의 수를 2개 또는 3개로 번갈아 가면서 지정

    cntShowBottle = 0 # 이번 게임에 보여줄 병 개수
    prevCntShowBottle = 0 # 앞 게임에 보여준 병 개수

    # 발모제에 대한 정보를 3번 전달함.
    for i in range(1, 4):
        ### 보여줄 병의 개수를 2개 또는 3개로 번갈아 임의로 선택
        # 4개의 물병준비
        # 인덱스에 해당하는 물병의 사용여부 저장
        bottle = [0, 0, 0, 0]

        # do ... while ... 문을 파이썬으로 구현하기
        while True:
            cntShowBottle = random.randint(0,1) + 2 # 보여줄 병 개수는 2-3개
            if cntShowBottle != prevCntShowBottle:
                break

        prevCntShowBottle = cntShowBottle

        ### 선택된 병의 개수만큼 병 선택

        # 발모제 포함여부에 따라 약의 효과여부 전달
        isincluded = 0 # 보여줄 병들에 발모제 포함 여부

        # 몇 번째 정보인지 알려줌.
        print(f" > {i} 번째 시도: ", end=' ')

        # 보여줄 병 종류 선택
        # 주의: 파이썬의 for 반복문은 사용되는 인덱스를 임의로 조정할 수 없음.
        # 따라서 while 반복문으로 대체함.
        
        j = 0
        while j < cntShowBottle:
            randBottle = random.randint(0,3)

            # 아직 선택되지 않은 물병만 선택
            if (bottle[randBottle] == 0):
                bottle[randBottle] = 1

                if (randBottle == treatment):
                    isincluded = 1  # 포함된 것 기억

                j += 1
        
        ### 사용자에게 준비된 3개의 물병조합 보여주기
        for k in range(0, 4):
            if (bottle[k] == 1):
                print(k+1, end=' ') 
        print(" 물약을 머리에 바릅니다.n")

        if (isincluded == 1):
            print(" >> 성공 ! 머리가 났어요 !!")
        else:
            print(" >> 실패 ! 머리가 나지 않었어요.. ㅠㅠ")

        input("\n ... 계속 하려면 아무 키나 누르세요 ...")
```

* 게임준비가 제대로 되는지 확인 가능.


```python
treatment = 2

game_setting(treatment)
```

     > 1 번째 시도:  2 4  물약을 머리에 바릅니다.n
     >> 실패 ! 머리가 나지 않었어요.. ㅠㅠ
    
     ... 계속 하려면 아무 키나 누르세요 ...
     > 2 번째 시도:  1 3 4  물약을 머리에 바릅니다.n
     >> 성공 ! 머리가 났어요 !!
    
     ... 계속 하려면 아무 키나 누르세요 ...
     > 3 번째 시도:  1 3  물약을 머리에 바릅니다.n
     >> 성공 ! 머리가 났어요 !!
    
     ... 계속 하려면 아무 키나 누르세요 ...


* `main()` 함수 부분은 쉽게 구현 가능함.


```python
# 아빠는 대머리 게임: 발모제 찾기

print("\n === 아빠는 대머리 게임 === \n")

# 4개의 물약 중에 효과 있는 발모제 임의 지정
treatment = random.randint(0,3)

# 게임 준비
game_setting(treatment)

# 사용자로부터 발모제 선택 입력값 받기
answer = int(input("\n\n 발모제는 몇 번일까요? "))

if (answer == treatment + 1):
    print("\n >> 정답입니다!")
else:
    print("\n >> 땡! 틀렸어요. 정답은 %d 입니다.", treatment + 1)
```

    
     === 아빠는 대머리 게임 === 
    
     > 1 번째 시도:  1 2 3  물약을 머리에 바릅니다.n
     >> 성공 ! 머리가 났어요 !!
    
     ... 계속 하려면 아무 키나 누르세요 ...
     > 2 번째 시도:  1 4  물약을 머리에 바릅니다.n
     >> 성공 ! 머리가 났어요 !!
    
     ... 계속 하려면 아무 키나 누르세요 ...
     > 3 번째 시도:  1 2 4  물약을 머리에 바릅니다.n
     >> 성공 ! 머리가 났어요 !!
    
     ... 계속 하려면 아무 키나 누르세요 ...
    
    
     발모제는 몇 번일까요? 2
    
     >> 땡! 틀렸어요. 정답은 %d 입니다. 1


---

## 연습문제

1. "아빠는 대머리 게임: 발모제 찾기" 코드에서 사용된 `game_setting()` 함수의 본체가 매우 길다.
    하지만 본체의 기능을 세분화할 수 있어 보인다.
    세분화가능한 부분을 함수로 선언해서 
    `game_setting()` 함수를, 그리고 결국엔 코드 전체를 보다 기능별로 분화된 보다 체계적인 코드로 
    구현하라.
