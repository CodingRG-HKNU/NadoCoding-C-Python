# 5장 함수

## 핵심

* 함수 개념
* 함수 정의

## (C 언어) 비밀번호 마스터

* 동영상: [(나도코딩 C) 5-1 비밀번호 마스터](https://www.youtube.com/watch?v=hwerIdYt_Mo&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=27&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9)

### 게임 설명

* 퀴즈를 맞히면서 문을 하나씩 열면서 전진하기

---

## (C 언어) 계산기

* 동영상: [(나도코딩 C) 5-2 계산기](https://www.youtube.com/watch?v=hL3AjJX-bY8&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=28&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9)

#### 함수 활용

* 선언을 먼저한 후에 정의를 나중에 할  수 있음.

---
```c
#include <stdio.h>
 
// 계산기
 
// 함수 선언
void p(int num);

int main()
{
	int num = 12;
	p(num);

	num /= 2;
	p(num);
     
    return 0;
}

// 함수 정의
void p(int num)
{
	printf("num은 %d 입니다.\n", num);
}
```

---

### Python 구현

* 파이썬에서는 함수 선언과 정의를 동시에 진행해야 함.
* 또한 함수가 실제로 호출되기 이전에 정의되어야 함.


```python
# 계산기
 
# 함수 선언 및 정의
# f-문자열 활용
def p(num):
    print(f"num은 {num}입니다.")

num = 12
p(num)

num /= 2
p(num)
```

    num은 12입니다.
    num은 6.0입니다.


#### 주의사항

* `print` 또한 이미 하나의 함수임.
* 하지만 여기서는 함수를 정의하는 방법을 소개하기 위한 예제로 사용했음.

---

## (C 언어) 함수의 형태

* 동영상: [(나도코딩 C) 5-3 함수의 형태](https://www.youtube.com/watch?v=x-J-wWFBDtY&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=29)

### 함수 정의 형식

---
```c
반환(자료)형 함수이름(자료형1 매개변수1, 자료형2 매개변수2, ..., 자료형k 매개변수k)
{
    명령문;
    ...
    return 반환값
}
```
---

* 반환형은 반환값의 자료형이 사용되어야 함.

* 함수를 미리 선언만 할 때 반환형과 매개변수들의 자료형이 동일하게 선언되어야 함.
    * 아래 코드에서 함수 `p()`의 반환형으로 `void`가 사용된 이유는 `printf()` 함수의 반환형이 `void`이기 때문.

---
```c
#include <stdio.h>
 
void p(int num);

int main()
{
	int num = 12;
	p(num);

    return 0;
}

// 함수 정의
void p(int num)
{
	printf("num은 %d 입니다.\n", num);
}
```

---

### Python 구현

* 파이썬에서는 함수 선언과 정의를 동시에 진행해야 함.
* 반환형 지정: 사용하지 않음.

#### 함수 정의 형식

```python
def 함수이름(매개변수1, 매개변수2, ..., 매개변수k):
    명령문
    return 반환값
```

* 반환값이 지정되지 않으면 `None`을 반환하도록 자동 설정됨:

    ```python
    return None
    ```

#### 유형 암시(typing hint)

* 파이썬 3.6 버전부터 C 언어의 정적 타이핑 방식이 형식적으로 지원됨.
* 주의: 정적 타이핑의 흉내만 낼 뿐, 실행과는 전혀 상관 없음.


```python
# 계산기

# 함수 선언 및 정의
# 매개변수 유형과 반환형 명시 가능
def p(num:int) -> None:
    print(f"num은 {num}입니다.")

num:int = 12
p(num)

num /= 2
p(num)
```

    num은 12입니다.
    num은 6.0입니다.


* 주의: 엉뚱한 유형 암시도 아무 문제를 발생시키지 않음.
    즉, 말 그대로 유형 암시일 뿐 실제 실행과는 무관함.


```python
def p(num:int) -> str:
    print(f"num은 {num}입니다.")

num:int = 12
p(num)

num /= 2
p(num)
```

    num은 12입니다.
    num은 6.0입니다.


* 리스트의 경우도 포함될 리스트의 자료형을 명시해 놓고 사용 가능.


```python
from typing import List # 대문자 L 사용에 주의

def total(xs: List[float]) -> float:
    return sum(xs)
```

* 보다 상세한 설명은 아래 두 사이트 참조
    * [파이썬 타입 어노테이션/힌트](https://www.daleseo.com/python-type-annotations/)
    * [파이썬 typing 모듈로 타입 표시하기](https://www.daleseo.com/python-typing/)
    
* 유형이 암시된대로의 작동여부 확인을 위해서는 mypy 라는 패키지를 설치해야 함. 사용법은 아래 사이트 참조
    * [파이썬 타입 체크 - Mypy](https://www.daleseo.com/python-mypy/)

---

## (C 언어) 반환값이 없는 함수

* 동영상: [(나도코딩 C) 5-4 반환값이 없는 함수](https://www.youtube.com/watch?v=k5F7f3AvHZY&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=30)

* 반환값이 없는 함수. 즉, 반환 자료형이 `void`
* 아래 형식을 따름:

---
```c
void 함수이름(자료형1 매개변수1, 자료형2 매개변수2, ..., 자료형k 매개변수k)
{
    명령문;
    ...
    // return 명령문이 사용되지 않아야 함
}
```

---
```c
#include <stdio.h>
 
// 함수 선언

void function_without_return();

int main()
{
	function_without_return();

    return 0;
}

// 함수 정의
// 반환값이 없는 함수
void function_without_return()
{
	printf("반환값이 없는 함수입니다.\n");
}
```

#### 함수 선언과 정의

* 함수 선언은 함수가 호출되기 이전에 지정되어 있어야 함.
    * 일반적으로 `main` 함수 이전에 선언함.
* 함수 정의는 이후에 아무 때나 하면 됨.
    * 일반적으로 `main` 함수 밖에서 정의됨.

---

### Python 구현


```python
# 함수 선언

# 반환값이 없는 함수d
def function_without_return():
    print("반환값이 없는 함수입니다.")

function_without_return()
```

    반환값이 없는 함수입니다.


---

## (C 언어) 반환값이 있는 함수

* 동영상: [(나도코딩 C) 5-5 반환값이 있는 함수](https://www.youtube.com/watch?v=qi4kIgEVqX4&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=31)

* 반환값이 있는 함수. 즉, 반환 자료형이 반환값의 자료형으로 지정되어야 함.
* 아래 형식을 따름:

---
```c
반환형 함수이름(자료형1 매개변수1, 자료형2 매개변수2, ..., 자료형k 매개변수k)
{
    명령문;
    ...
    return 반환값
}
```

---
```c
#include <stdio.h>
 
// 함수 선언

void p(int num);
int function_with_return();

int main()
{
	int ret = function_with_return();
    p(ret);

    return 0;
}

// 함수 정의
void p(int num)
{
	printf("num은 %d 입니다.\n", num);
}

// 반환값이 있는 함수
int function_with_return()
{
	printf("반환값이 있는 함수입니다.\n");
    return 10;
}
```

---

### Python 구현


```python
# 함수 정의
def p(num):
    print(f"num은 {num}입니다.")

# 반환값이 있는 함수
def function_with_return():
    print("반환값이 있는 함수입니다.")
    return 10

ret = function_with_return()
p(ret)
```

    반환값이 있는 함수입니다.
    num은 10입니다.


---

## (C 언어) 파라미터(전달값)이 없는 함수

* 동영상: [(나도코딩 C) 5-6 전달값이 없는 함수](https://www.youtube.com/watch?v=VAGucb4u_QE&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=32)

* 파라미터(전달값)이 전혀 사용되지 않는 함수
* 함수 호출할 때 반드시 괄호 사용해야 함.
* 반환형은 있어도/없어도 됨.
* 아래 형식을 따름:

---
```c
반환형 함수이름()
{
    명령문;
    ...
}
```

---
```c
#include <stdio.h>
 
// 함수 선언

void function_without_params();

int main()
{
	function_without_params();

    return 0;
}

// 함수 정의
// 전달값이 없는 함수
void function_without_params()
{
	printf("전달값이 없는 함수입니다.\n");
 }
```

---

### Python 구현


```python
# 전달값이 없는 함수

def function_without_params():
    print("전달값이 없는 함수입니다.")

function_without_params()
```

    전달값이 없는 함수입니다.


---

## (C 언어) 파라미터(전달값)이 있는 함수

* 동영상: [(나도코딩 C) 5-7 전달값이 있는 함수](https://www.youtube.com/watch?v=AtzogzNw5EA&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=33)

* 파라미터(전달값)이 사용되는 함수
* 함수 호출할 때 반드시 적절한 수의 인자와 함께 사용해야 함.
* 반환값은 있어도 없어도 됨.
* 아래 형식을 따름:

---
```c
반환형 함수이름(자료형1 매개변수1, 자료형2 매개변수2, ..., 자료형k 매개변수k)
{
    명령문;
    ...
}
```

---
```c
#include <stdio.h>
 
// 함수 선언

void function_with_params(int num1, int num2, int num3);

int main()
{
	function_with_params(35, 27, 12);

    return 0;
}

// 함수 정의
// 전달값이 있는 함수
void function_with_params(int num1, int num2, int num3)
{
	printf("전달값이 있는 함수이며, 전달받은 값은 %d, %d, %d 입니다.\n", num1, num2, num3);
}
```

---

### Python 구현


```python
## 전달값이 있는 함수
def function_with_params(num1, num2, num3):
    print(f"전달값이 있는 함수이며, 전달받은 값은 {num1}, {num2}, {num3} 입니다.")

function_with_params(35, 27, 12)
```

    전달값이 있는 함수이며, 전달받은 값은 35, 27, 12 입니다.


---

## (C 언어) 반환값과 파라미터(전달값)이 있는 함수

* 동영상: [(나도코딩 C) 5-8 반환값과 전달값이 있는 함수](https://www.youtube.com/watch?v=zsr5u4gI7Zo&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=34)

* 반환값과 파라미터(전달값) 모두 사용되는 함수
* 함수 호출할 때 반드시 적절한 수의 인자와 함께 사용해야 함.
* 반환값이 반드시 적절하게 명시되어야 함.
* 아래 형식을 따름:

---
```c
반환형 함수이름(자료형1 매개변수1, 자료형2 매개변수2, ..., 자료형k 매개변수k)
{
    명령문;
    ...
    return 반환값
}
```

* 반환값을 저장하여 활용 가능

---
```c
#include <stdio.h>
 
// 함수 선언

int apple(int total, int ate); // 전체 total 개에서 ate 개를 먹고 남은 수를 반환


int main()
{
	// 5개의 사과 중에서 2개 먹기
    // 반환값을 저장 후 활용
	int ret = apple(5, 2);
	printf("사과 5개 중에 2개를 먹으면? %d 개가 남아요.\n", ret);

    return 0;
}

// 함수 정의
// 파라미터(전달값)도 받고, 반환값도 있는 함수
int apple(int total, int ate)
{
	return (total - ate);
}
```

* 반환값을 직접 활용 가능

---
```c
#include <stdio.h>
 
// 함수 선언

int apple(int total, int ate); // 전체 total 개에서 ate 개를 먹고 남은 수를 반환


int main()
{
	// 5개의 사과 중에서 2개 먹기
    // 함수의 반환값 직접 활용
	printf("사과 %d 개 중에 %d 개를 먹으면? %d 개가 남아요.\n", 10, 4, apple(10,4));

    return 0;
}

// 함수 정의
// 파라미터(전달값)도 받고, 반환값도 있는 함수
int apple(int total, int ate)
{
	return (total - ate);
}
```

---

### Python 구현

* 반환값을 저장하여 활용 가능


```python
# 함수 정의
# 파라미터(전달값)도 받고, 반환값도 있는 함수
def apple(total, ate):
    return (total - ate)

# 5개의 사과 중에서 2개 먹기
# 반환값을 저장 후 활용

ret = apple(5, 2)
print(f"사과 5개 중에 2개를 먹으면? {ret} 개가 남아요.")
```

    사과 5개 중에 2개를 먹으면? 3 개가 남아요.


* 반환값을 직접 활용 가능


```python
# 함수 정의
# 파라미터(전달값)도 받고, 반환값도 있는 함수
def apple(total, ate):
    return (total - ate)

# 5개의 사과 중에서 2개 먹기
# 반환값 직접 활용

print(f"사과 {10}개 중에 {4}개를 먹으면? {apple(10,4)} 개가 남아요.")
```

    사과 10개 중에 4개를 먹으면? 6 개가 남아요.


---

## (C 언어) 함수를 이용한 계산기

* 동영상: [(나도코딩 C) 5-9 함수를  이용한 계산기](https://www.youtube.com/watch?v=1Hbw87QrP54&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=35)

#### 함수 활용 예제: 사칙연산을 실행하는 함수 선언하여 활용하기

---
```c
#include <stdio.h>

// 함수 선언
// 출력 함수 새로 선언
void p(int num);

// 계산기 함수
int add(int num1, int num2);
int sub(int num1, int num2);
int mul(int num1, int num2);
int div(int num1, int num2);


int main()
{
	int num = 2;
	num = add(num, 3);
	p(num);

	num = sub(num, 1);
	p(num);

	num = mul(num, 3);
	p(num);

	num = div(num, 6);
	p(num);
    return 0;
}

// 함수 정의
void p(int num)
{
	printf("num은 %d 입니다.\n", num);
}

int add(int num1, int num2)
{
	return num1 + num2;
}

int sub(int num1, int num2)
{
	return num1 - num2;
}

int mul(int num1, int num2)
{
	return num1 * num2;
}

int div(int num1, int num2)
{
	return num1 / num2;
}
```

---

### Python 구현


```python
# 함수 정의
def p(num):
    print(f"num은 {num} 입니다.")

def add(num1, num2):
    return num1 + num2

def sub(num1, num2):
    return num1 - num2

def mul(num1, num2):
    return num1 * num2

def div(num1, num2):
    return num1 / num2

num = 2

num = add(num, 3)
p(num)

num = sub(num, 1)
p(num)

num = mul(num, 3)
p(num)

num = div(num, 6)
p(num)
```

    num은 5 입니다.
    num은 4 입니다.
    num은 12 입니다.
    num은 2.0 입니다.


---

## (C 언어) 프로젝트

* 동영상: [(나도코딩 C) 5-10 프로젝트](https://www.youtube.com/watch?v=3L8WqhdIF0I&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=36)

#### 5단계로 이루어진 곱셈 계산 맞히기 게임

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

// 함수 선언
// 계산기 함수
int getRandomNumber(int level);
void showQuestion(int level, int num1, int num2);
void success();
void fail();

int main()
{
	// 문이 5개가 있고, 각 문마다 어려운 수식퀴즈가 출제(랜덤)
	// 맞히면 통과, 틀리면 실패

	srand(time(NULL));
	int count = 0;           // 맞힌 문제수
	for (int i=1; i<=5; i++)
	{
		// x * y = ?
		int num1 = getRandomNumber(i);
		int num2 = getRandomNumber(i);
		//printf("%d x %d ?"), num1, num2);
		showQuestion(i, num1, num2);

		int answer = -1;

		scanf("%d", &answer);
        
        // (answer == -1)의 경우의 기능은 두 가지
        // 첫째: 게임을 종료하고자 할 경우 -1 입력
        // 둘째: 예외처리 기능
        //      숫자 이외의 엉뚱한 값이 입력될 경우 answer에 할당된 값이 변하지 않기 때문임.
		if (answer == -1)
		{
			printf("프로그램을 종료합니다.\n");
			exit(0);  // 프로그램 종료!
		}
		else if (answer == num1 * num2)
		{
			// 성공
			success();
			count++;
		}
		else
		{
			// 실패
			fail();
		}
	}

	printf("\n\n 당신은 5개의 비밀번호 중 %d 개를 맞혔습니다.\n", count);

    return 0;
}

// 함수 정의
int getRandomNumber(int level)
{
	// 0을 피하기 위해 +1 사용
	return rand() % (level * 7) + 1;
}

void showQuestion(int level, int num1, int num2)
{
	printf("\n\n\n### %d 번째 비밀번호 ###\n", level);
	printf("\n\t%d x %d 는? \n\n", num1, num2);
	printf("#######################\n");
	printf("\n비밀번호를 입력하세요 (종료: -1) >> ");
}

void success()
{
	printf("\n >> Good! 정답입니다.\n");
}

void fail()
{
	printf("\n >> 땡! 틀렸습니다.\n");
}
```

---

### Python 구현


```python
import random 
import time
import sys

## 현재 시간에 맞추어 무작위로 정수 생성 가능
# time 함수: 1970.01.01 이후 흐른 시간(ns 단위)
current_time = int(time.time())
# 현재 시간 기준으로 무작위수 생성 지정
random.seed(current_time)

# 함수 정의
def getRandomNumber(level):
    # 0을 피하기 위해 +1 사용
    return random.randint(0, sys.maxsize) % (level * 7) + 1

def showQuestion(level, num1, num2):
    print("\n\n\n### %d 번째 비밀번호 ###\n" % level)
    print("\n\t%d x %d 는? \n\n" % (num1, num2))
    print("#######################\n")
    print("\n비밀번호를 입력하세요 (종료: -1) >> ")

def success():
    print("\n >> Good! 정답입니다.\n")

def fail():
    print("\n >> 땡! 틀렸습니다.\n")

# 문이 5개가 있고, 각 문마다 어려운 수식퀴즈가 출제(랜덤)
# 맞히면 통과, 틀리면 실패

count = 0           # 맞힌 문제수

for i in range(1,6):
    # x * y = ?
    num1 = getRandomNumber(i)
    num2 = getRandomNumber(i)
    #printf("%d x %d ?"), num1, num2)
    showQuestion(i, num1, num2)

    # 정수가 아닌 엉뚱한 답변 예외처리하기
    try:
        answer = int(input("답을 입력하세요: "))
    except:
        print("정수를 입력하지 않았습니다.")
        print("프로그램을 종료합니다.\n")
        sys.exit(0)

    # 정수가 입력된 경우
    if (answer == -1):
        print("프로그램을 종료합니다.\n")
        sys.exit(0)        
        
    elif (answer == num1 * num2):
        # 성공
        success()
        count = count + 1
    else:
        # 실패
        fail()

print("\n\n 당신은 5개의 비밀번호 중 %d 개를 맞혔습니다.\n" % count)
```

    
    
    
    ### 1 번째 비밀번호 ###
    
    
    	7 x 5 는? 
    
    
    #######################
    
    
    비밀번호를 입력하세요 (종료: -1) >> 
    답을 입력하세요: 35
    
     >> Good! 정답입니다.
    
    
    
    
    ### 2 번째 비밀번호 ###
    
    
    	1 x 5 는? 
    
    
    #######################
    
    
    비밀번호를 입력하세요 (종료: -1) >> 
    답을 입력하세요: 5
    
     >> Good! 정답입니다.
    
    
    
    
    ### 3 번째 비밀번호 ###
    
    
    	17 x 13 는? 
    
    
    #######################
    
    
    비밀번호를 입력하세요 (종료: -1) >> 
    답을 입력하세요: 221
    
     >> Good! 정답입니다.
    
    
    
    
    ### 4 번째 비밀번호 ###
    
    
    	19 x 6 는? 
    
    
    #######################
    
    
    비밀번호를 입력하세요 (종료: -1) >> 
    답을 입력하세요: 114
    
     >> Good! 정답입니다.
    
    
    
    
    ### 5 번째 비밀번호 ###
    
    
    	30 x 26 는? 
    
    
    #######################
    
    
    비밀번호를 입력하세요 (종료: -1) >> 
    답을 입력하세요: 780
    
     >> Good! 정답입니다.
    
    
    
     당신은 5개의 비밀번호 중 5 개를 맞혔습니다.
    


---
