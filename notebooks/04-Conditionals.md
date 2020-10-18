# 4장 조건문

## 핵심: 조건과 분기

* `if ... else`
* `break`
* `continue`
* `switch`

## (C 언어) 숫자 맞히기 Up&Down

* 동영상: [(나도코딩 C) 4-1 숫자 맞히기 Up&Down](https://www.youtube.com/watch?v=62pWle2i3ek&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=21)

### 게임 설명

* 상대방이 생각한 1부터 100사이의 수를 맞히는 게임
* 언급한 숫자가 맞혀야 하는 숫자보다 크면 Down으로 반응
* 언급한 숫자가 맞혀야 하는 숫자보다 크면 Up으로 반응
* 지정된 횟수 안에 지정된 숫자를 맞혀야 함

## (C 언어) `if ... else`

* 동영상: [(나도코딩 C) 4-2 If Else](https://www.youtube.com/watch?v=9dxy-eG8gvI&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=22)

### 형식

```c
if (조건)
    {
        명령문
    }
else
    {
        명령문
    }
```

### 예제: `if ... else ...`

```c
#include <stdio.h>

int main(void) {
    /*
	버스를 탄다고 가정
	학생/일반인으로 구분
	일반인: 20세 이상
	*/
    
    int age = 15;
	if (age >= 20)
        printf("일반인입니다.\n");
    else
        printf("학생입니다.\n");

    return 0;

}
```

---

### Python 구현

* 파이썬에서도 사실상 동일한 조건문 형식 사용
* 파이썬의 여러 줄 주석은 세 개의 큰인용부호 사용.


```python
"""
버스를 탄다고 가정
학생/일반인으로 구분
일반인: 20세 이상
"""
    
age = 15
if (age >= 20):
    print("일반인입니다.")
else:
    print("학생입니다.")
```

---

### 예제: `if ... else if ... else`

```c
#include <stdio.h>

int main(void) {
    /*
	초등학생(8-13)/중학생(14-16)/고등학생(17-19)/일반인으로 구분하기

	if ... else if ... else 형식 활용
	*/
    
    int age = 25;
	if (age >= 8 && age <= 13)
        printf("초등학생입니다.\n");
    else if (age >= 14 && age <= 16)
        printf("중학생입니다.\n");
    // else if 반복 사용 가능
	else if (age >= 17 && age <= 19)
        printf("고등학생입니다.\n");
    // 마지막 남은 경우는 else로 처리
    else
        printf("일반인입니다.\n");

    return 0;

}
```

#### PythonTutor 활용하기

* [(C 언어) if ... else if ... else](http://pythontutor.com/visualize.html#code=%23include%20%3Cstdio.h%3E%0A%0Aint%20main%28void%29%20%7B%0A%20%20%20%20/*%0A%20%20%20%20%EC%B4%88%EB%93%B1%ED%95%99%EC%83%9D%288-13%29/%EC%A4%91%ED%95%99%EC%83%9D%2814-16%29/%EA%B3%A0%EB%93%B1%ED%95%99%EC%83%9D%2817-19%29/%EC%9D%BC%EB%B0%98%EC%9D%B8%EC%9C%BC%EB%A1%9C%20%EA%B5%AC%EB%B6%84%ED%95%98%EA%B8%B0%0A%0A%20%20%20%20if%20...%20else%20if%20...%20else%20%ED%98%95%EC%8B%9D%20%ED%99%9C%EC%9A%A9%0A%20%20%20%20*/%0A%20%20%20%20%0A%20%20%20%20int%20age%20%3D%2025%3B%0A%20%20%20%20if%20%28age%20%3E%3D%208%20%26%26%20age%20%3C%3D%2013%29%0A%20%20%20%20%20%20%20%20printf%28%22%EC%B4%88%EB%93%B1%ED%95%99%EC%83%9D%EC%9E%85%EB%8B%88%EB%8B%A4.%5Cn%22%29%3B%0A%20%20%20%20else%20if%20%28age%20%3E%3D%2014%20%26%26%20age%20%3C%3D%2016%29%0A%20%20%20%20%20%20%20%20printf%28%22%EC%A4%91%ED%95%99%EC%83%9D%EC%9E%85%EB%8B%88%EB%8B%A4.%5Cn%22%29%3B%0A%20%20%20%20//%20else%20if%20%EB%B0%98%EB%B3%B5%20%EC%82%AC%EC%9A%A9%20%EA%B0%80%EB%8A%A5%0A%20%20%20%20else%20if%20%28age%20%3E%3D%2017%20%26%26%20age%20%3C%3D%2019%29%0A%20%20%20%20%20%20%20%20printf%28%22%EA%B3%A0%EB%93%B1%ED%95%99%EC%83%9D%EC%9E%85%EB%8B%88%EB%8B%A4.%5Cn%22%29%3B%0A%20%20%20%20//%20%EB%A7%88%EC%A7%80%EB%A7%89%20%EB%82%A8%EC%9D%80%20%EA%B2%BD%EC%9A%B0%EB%8A%94%20else%EB%A1%9C%20%EC%B2%98%EB%A6%AC%0A%20%20%20%20else%0A%20%20%20%20%20%20%20%20printf%28%22%EC%9D%BC%EB%B0%98%EC%9D%B8%EC%9E%85%EB%8B%88%EB%8B%A4.%5Cn%22%29%3B%0A%0A%20%20%20%20return%200%3B%0A%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)

---

### Python 구현

* 파이썬에서도 사실상 동일한 조건문 형식 사용
* 단, `else if` 대신에 `elif` 사용.
* 또한 사용된 논리 연산자에도 주의할 것

| 논리 연산자 | C 언어 | Python 언어 |
| ---: | :---:  | :---: |
| 논리곱($\land$) | && | and |
| 논리합($\lor$) | &#124;&#124; | or |
| 논리부정($\neg$) | ! | not |


```python
"""
초등학생(8-13)/중학생(14-16)/고등학생(17-19)/일반인으로 구분하기

if ... else if ... else 형식 활용
"""
    
age = 25

if (age >= 8 and age <= 13):
    print("초등학생입니다.")
elif (age >= 14 and age <= 16):
    print("중학생입니다.")
# elif 반복 사용 가능
elif (age >= 17 and age <= 19):
    print("고등학생입니다.")
# 마지막 남은 경우는 else로 처리
else:
    print("일반인입니다.")
```

---

## (C 언어) `break/continue`

* 동영상: [(나도코딩 C) 4-3 Break Continue](https://www.youtube.com/watch?v=T-IiUqRbeu4&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=23)

### `break`

* `break`가 실행되는 순간에 가장 가까운 반복문의 실행 종료

### 예제: `break`

```c
#include <stdio.h>

int main(void) {
    /*
	break/continue
	
	1번부터 30번까지 있는 반에서 1번에서 5번까지 조별 발표하기
	*/

	for (int i = 1; i <=30; i++)
	{
		if (i >= 6)
		{
			printf("나머지 학생은 집에 가세요.\n");
			// 이제 for 반복문을 더이상 실행하지 않도록 하기
			break;        
		}
		printf("%d번 학생은 조별발표 준비 하세요.\n", i);
	}

    return 0; 

}
```

#### PythonTutor 활용하기

* [(C 언어) break](http://pythontutor.com/visualize.html#code=%23include%20%3Cstdio.h%3E%0A%0Aint%20main%28void%29%20%7B%0A%20%20%20%20/*%0A%20%20%20%20break/continue%0A%20%20%20%20%0A%20%20%20%201%EB%B2%88%EB%B6%80%ED%84%B0%2030%EB%B2%88%EA%B9%8C%EC%A7%80%20%EC%9E%88%EB%8A%94%20%EB%B0%98%EC%97%90%EC%84%9C%201%EB%B2%88%EC%97%90%EC%84%9C%205%EB%B2%88%EA%B9%8C%EC%A7%80%20%EC%A1%B0%EB%B3%84%20%EB%B0%9C%ED%91%9C%ED%95%98%EA%B8%B0%0A%20%20%20%20*/%0A%0A%20%20%20%20for%20%28int%20i%20%3D%201%3B%20i%20%3C%3D30%3B%20i%2B%2B%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20if%20%28i%20%3E%3D%206%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22%EB%82%98%EB%A8%B8%EC%A7%80%20%ED%95%99%EC%83%9D%EC%9D%80%20%EC%A7%91%EC%97%90%20%EA%B0%80%EC%84%B8%EC%9A%94.%5Cn%22%29%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20//%20%EC%9D%B4%EC%A0%9C%20for%20%EB%B0%98%EB%B3%B5%EB%AC%B8%EC%9D%84%20%EB%B9%A0%EC%A0%B8%EB%82%98%EC%98%A4%EB%8F%84%EB%A1%9D%20%ED%95%B4%EC%95%BC%20%ED%95%A8.%0A%20%20%20%20%20%20%20%20%20%20%20%20break%3B%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20printf%28%22%25d%EB%B2%88%20%ED%95%99%EC%83%9D%EC%9D%80%20%EC%A1%B0%EB%B3%84%EB%B0%9C%ED%91%9C%20%EC%A4%80%EB%B9%84%20%ED%95%98%EC%84%B8%EC%9A%94.%5Cn%22,%20i%29%3B%0A%20%20%20%20%7D%0A%0A%20%20%20%20return%200%3B%20%0A%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)

---

### Python 구현

* 파이썬에서 break 명령문의 역할은 동일함.


```python
"""
break/continue

1번부터 30번까지 있는 반에서 1번에서 5번까지만 조별 발표하기
"""

for i in range(1, 31):
    if (i >= 6):
        print("나머지 학생은 집에 가세요.")
        # 이제 for 반복문을 더이상 실행하지 않도록 하기위해 break 사용
        break        
    print(f"{i}번 학생은 조별발표 준비 하세요.")
```

---

### `continue`

* `continue`가 실행되는 순간에 가장 가까운 반복문의 다음 경우 실행

### 예제: `continue`

```c
#include <stdio.h>

int main(void) {
    /*
	break/continue
	
	1번부터 30번까지 있는 반에서 7번 학생은 결석
	따라서 7번을 제외하고 6번부터 10번까지 조별발표 하세요.
	*/

	for (int i = 1; i <=30; i++)
	{
		if (i >= 6 && i <= 10)
		{
			if (i == 7)
			{
			printf("%d번 학생은 결석입니다.\n", i);
			// 이제 7번 학생은 건너뛰고 for 반복문을 8번 학생에 대해 실행하도록 하기
			continue ;
			}        
		
			printf("%d번 학생은 조별발표 준비 하세요.\n", i);
		}
	}

    return 0; 

}
```

#### PythonTutor 활용하기

* [(C 언어) continue](http://pythontutor.com/visualize.html#code=%23include%20%3Cstdio.h%3E%0A%0Aint%20main%28void%29%20%7B%0A%20%20%20%20/*%0A%20%20%20%20break/continue%0A%20%20%20%20%0A%20%20%20%201%EB%B2%88%EB%B6%80%ED%84%B0%2030%EB%B2%88%EA%B9%8C%EC%A7%80%20%EC%9E%88%EB%8A%94%20%EB%B0%98%EC%97%90%EC%84%9C%207%EB%B2%88%20%ED%95%99%EC%83%9D%EC%9D%80%20%EA%B2%B0%EC%84%9D%0A%20%20%20%20%EB%94%B0%EB%9D%BC%EC%84%9C%207%EB%B2%88%EC%9D%84%20%EC%A0%9C%EC%99%B8%ED%95%98%EA%B3%A0%206%EB%B2%88%EB%B6%80%ED%84%B0%2010%EB%B2%88%EA%B9%8C%EC%A7%80%20%EC%A1%B0%EB%B3%84%EB%B0%9C%ED%91%9C%20%ED%95%98%EC%84%B8%EC%9A%94.%0A%20%20%20%20*/%0A%0A%20%20%20%20for%20%28int%20i%20%3D%201%3B%20i%20%3C%3D30%3B%20i%2B%2B%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20if%20%28i%20%3E%3D%206%20%26%26%20i%20%3C%3D%2010%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20if%20%28i%20%3D%3D%207%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22%25d%EB%B2%88%20%ED%95%99%EC%83%9D%EC%9D%80%20%EA%B2%B0%EC%84%9D%EC%9E%85%EB%8B%88%EB%8B%A4.%5Cn%22,%20i%29%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20//%20%EC%9D%B4%EC%A0%9C%207%EB%B2%88%20%ED%95%99%EC%83%9D%EC%9D%80%20%EA%B1%B4%EB%84%88%EB%9B%B0%EA%B3%A0%20for%20%EB%B0%98%EB%B3%B5%EB%AC%B8%20%EC%9D%B4%EC%96%B4%EB%82%98%EA%B0%80%EB%8F%84%EB%A1%9D%20%ED%95%B4%EC%95%BC%ED%95%A8.%0A%20%20%20%20%20%20%20%20%20%20%20%20continue%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22%25d%EB%B2%88%20%ED%95%99%EC%83%9D%EC%9D%80%20%EC%A1%B0%EB%B3%84%EB%B0%9C%ED%91%9C%20%EC%A4%80%EB%B9%84%20%ED%95%98%EC%84%B8%EC%9A%94.%5Cn%22,%20i%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%0A%20%20%20%20return%200%3B%20%0A%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)

---

### Python 구현

* 파이썬에서 continue 명령문의 역할은 동일함.


```python
"""
break/continue

1번부터 30번까지 있는 반에서 7번 학생은 결석
따라서 7번을 제외하고 6번부터 10번까지 조별발표 하세요.
"""

for i in range(1, 31):
    if (i >= 6 and i <= 10):
        if (i == 7):
            print("%d번 학생은 결석입니다." % i)
            # 이제 7번 학생은 건너뛰고 for 반복문을 8번 학생에 대해 실행하도록 하기
            continue 

        print("%d번 학생은 조별발표 준비 하세요." % i)
```

* 파이썬에서 숫자들의 구간은 보다 쉽게 표현할 수 있음.
* `i >= 6 and i <= 10` 를 `6 <= i <= 10` 표현 가능.


```python
"""
break/continue

1번부터 30번까지 있는 반에서 7번 학생은 결석
따라서 7번을 제외하고 6번부터 10번까지 조별발표 하세요.
"""

for i in range(1, 31):
    if (6 <= i <= 10):
        if (i == 7):
            print("%d번 학생은 결석입니다." % i)
            # 이제 7번 학생은 건너뛰고 for 반복문을 8번 학생에 대해 실행하도록 하기
            continue 

        print("%d번 학생은 조별발표 준비 하세요." % i)
```

    6번 학생은 조별발표 준비 하세요.
    7번 학생은 결석입니다.
    8번 학생은 조별발표 준비 하세요.
    9번 학생은 조별발표 준비 하세요.
    10번 학생은 조별발표 준비 하세요.


### 중첩 반복문과 break/continue

* continue와 break 모두 자신을 직접 감싸는 반복문에 대해서만 작용함.

#### 중첩 반복문과 break

* 3과의 곱셈을 만나면 해당 구구단 멈추고 다음 단으로 이동.

```c
#include <stdio.h>
 
int main()
{
	for (int i = 2; i<= 9; i++)
	{
		for (int j = 1; j <= 9; j++)
		{
			if (j == 3)
			{
				break;
			}
			printf("%d 곱하기 %d는 %d\n", i, j, i*j);
		}

		printf("\n");
	}
	 
    return 0;
}
```

#### PythonTutor 활용하기

* [(C 언어) 이중 반복문과 break](http://pythontutor.com/visualize.html#code=%23include%20%3Cstdio.h%3E%0A%20%0Aint%20main%28%29%0A%7B%0A%20%20%20%20for%20%28int%20i%20%3D%202%3B%20i%3C%3D%209%3B%20i%2B%2B%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20j%20%3D%201%3B%20j%20%3C%3D%209%3B%20j%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20if%20%28j%20%3D%3D%203%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20break%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22%25d%20%EA%B3%B1%ED%95%98%EA%B8%B0%20%25d%EB%8A%94%20%25d%5Cn%22,%20i,%20j,%20i*j%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%0A%20%20%20%20%20%20%20%20printf%28%22%5Cn%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%20%0A%20%20%20%20return%200%3B%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)

#### Python 구현


```python
for i in range(2,10):
    for j in range(1,10):
        if j == 3:
            break
        print(f"{i} 곱하기 {j} 는 {i*j}")
    
    print('')
```

    2 곱하기 1 는 2
    2 곱하기 2 는 4
    
    3 곱하기 1 는 3
    3 곱하기 2 는 6
    
    4 곱하기 1 는 4
    4 곱하기 2 는 8
    
    5 곱하기 1 는 5
    5 곱하기 2 는 10
    
    6 곱하기 1 는 6
    6 곱하기 2 는 12
    
    7 곱하기 1 는 7
    7 곱하기 2 는 14
    
    8 곱하기 1 는 8
    8 곱하기 2 는 16
    
    9 곱하기 1 는 9
    9 곱하기 2 는 18
    


#### 중첩 반복문과 continue

* 3과의 곱셈을 만나면 건너뜀.

```c
#include <stdio.h>
 
int main()
{
	for (int i = 2; i<= 9; i++)
	{
		for (int j = 1; j <= 9; j++)
		{
			if (j == 3)
			{
				continue;
			}
			printf("%d 곱하기 %d는 %d\n", i, j, i*j);
		}

		printf("\n");
	}
	 
    return 0;
}
```

#### PythonTutor 활용하기

* [(C 언어) 중첩 반복문과 continue](http://pythontutor.com/visualize.html#code=%23include%20%3Cstdio.h%3E%0A%20%0Aint%20main%28%29%0A%7B%0A%20%20%20%20for%20%28int%20i%20%3D%202%3B%20i%3C%3D%209%3B%20i%2B%2B%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20j%20%3D%201%3B%20j%20%3C%3D%209%3B%20j%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20if%20%28j%20%3D%3D%203%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20continue%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%20%20%20%20printf%28%22%25d%20%EA%B3%B1%ED%95%98%EA%B8%B0%20%25d%EB%8A%94%20%25d%5Cn%22,%20i,%20j,%20i*j%29%3B%0A%20%20%20%20%20%20%20%20%7D%0A%0A%20%20%20%20%20%20%20%20printf%28%22%5Cn%22%29%3B%0A%20%20%20%20%7D%0A%20%20%20%20%20%0A%20%20%20%20return%200%3B%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)


```python
for i in range(2,10):
    for j in range(1,10):
        if j == 3:
            continue
        print(f"{i} 곱하기 {j} 는 {i*j}")
        
    print('')
```

    2 곱하기 1 는 2
    2 곱하기 2 는 4
    2 곱하기 4 는 8
    2 곱하기 5 는 10
    2 곱하기 6 는 12
    2 곱하기 7 는 14
    2 곱하기 8 는 16
    2 곱하기 9 는 18
    
    3 곱하기 1 는 3
    3 곱하기 2 는 6
    3 곱하기 4 는 12
    3 곱하기 5 는 15
    3 곱하기 6 는 18
    3 곱하기 7 는 21
    3 곱하기 8 는 24
    3 곱하기 9 는 27
    
    4 곱하기 1 는 4
    4 곱하기 2 는 8
    4 곱하기 4 는 16
    4 곱하기 5 는 20
    4 곱하기 6 는 24
    4 곱하기 7 는 28
    4 곱하기 8 는 32
    4 곱하기 9 는 36
    
    5 곱하기 1 는 5
    5 곱하기 2 는 10
    5 곱하기 4 는 20
    5 곱하기 5 는 25
    5 곱하기 6 는 30
    5 곱하기 7 는 35
    5 곱하기 8 는 40
    5 곱하기 9 는 45
    
    6 곱하기 1 는 6
    6 곱하기 2 는 12
    6 곱하기 4 는 24
    6 곱하기 5 는 30
    6 곱하기 6 는 36
    6 곱하기 7 는 42
    6 곱하기 8 는 48
    6 곱하기 9 는 54
    
    7 곱하기 1 는 7
    7 곱하기 2 는 14
    7 곱하기 4 는 28
    7 곱하기 5 는 35
    7 곱하기 6 는 42
    7 곱하기 7 는 49
    7 곱하기 8 는 56
    7 곱하기 9 는 63
    
    8 곱하기 1 는 8
    8 곱하기 2 는 16
    8 곱하기 4 는 32
    8 곱하기 5 는 40
    8 곱하기 6 는 48
    8 곱하기 7 는 56
    8 곱하기 8 는 64
    8 곱하기 9 는 72
    
    9 곱하기 1 는 9
    9 곱하기 2 는 18
    9 곱하기 4 는 36
    9 곱하기 5 는 45
    9 곱하기 6 는 54
    9 곱하기 7 는 63
    9 곱하기 8 는 72
    9 곱하기 9 는 81
    


---

## (C 언어) And/Or 부울 연산

* 동영상: [(나도코딩 C) 4-4 And Or 연산](https://www.youtube.com/watch?v=LjP9HlJBQ6s&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=24)

### 예제

* 아래 코드 실행하면 `값이 서로 다르네요` 출력

```c
#include <stdio.h>

int main(void) {
    /*
	논리 연산자: &&(and) 와 ||(or)
	*/

	int a = 10;
	int b = 11;
	int c = 12;
	int d = 13;
	if (a==b && c ==d)
	{
		printf("a와 b는 같고, c와 d도 같습니다.\n");
	}
	else
	{
		printf("값이 서로 다르네요.\n");
	}

    return 0; 

}
```

* 아래 코드 실행하면 `a와 b는 같고, c와 d도 같습니다.` 출력

```c
#include <stdio.h>

int main(void) {
    /*
	논리 연산자: &&(and) 와 ||(or)
	*/

	int a = 10;
	int b = 10;
	int c = 12;
	int d = 12;
	if (a==b && c ==d)
	{
		printf("a와 b는 같고, c와 d도 같습니다.\n");
	}
	else
	{
		printf("값이 서로 다르네요.\n");
	}

    return 0; 

}
```

* 아래 코드 실행하면 `a와 b, 혹은 c와 d의 값이 같습니다.` 출력

```c
#include <stdio.h>

int main(void) {
    /*
	논리 연산자: &&(and) 와 ||(or)
	*/

	int a = 10;
	int b = 10;
	int c = 12;
	int d = 13;
	if (a==b || c ==d)
	{
		printf("a와 b, 혹은 c와 d의 값이 같습니다.\n");
	}
	else
	{
		printf("값이 서로 다르네요.\n");
	}

    return 0; 

}
```

* 아래 코드 실행하면 `a와 b, 혹은 c와 d의 값이 같습니다.` 출력

```c
#include <stdio.h>

int main(void) {
    /*
	논리 연산자: &&(and) 와 ||(or)
	*/

	int a = 11;
	int b = 10;
	int c = 12;
	int d = 12;
	if (a==b || c ==d)
	{
		printf("a와 b, 혹은 c와 d의 값이 같습니다.\n");
	}
	else
	{
		printf("값이 서로 다르네요.\n");
	}

    return 0; 

}
```

---

### Python 구현


```python

```

---

## (C 언어) switch ... case ...

* 동영상: [(나도코딩 C) 4-5 Switch Case](https://www.youtube.com/watch?v=NJpK3RgKDS8&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=25&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9)

### 예제

* `if ... else if ... else`를 이용한 가위-바위-보 게임

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void) {
    /*
	가위 0, 바위 1, 보 2
	*/

	srand(time(NULL));
	int i = rand() % 3;   // 0부터 2 사이 숫자 반환

	if (i == 0)
	{
		printf("가위!\n");
	}
	else if (i == 1)
	{
		printf("바위!\n");
	}
	else if (i == 2)
	{
		printf("보!\n");
	}
	else
	{
		printf("몰라요!\n");
	}

    return 0; 

}
```

* `switch ... case ...`를 이용한 가위-바위-보 게임
* `break` 사용에 주의할 것!

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void) {
    /*
	switch 활용: 가위 0, 바위 1, 보 2
	*/

	srand(time(NULL));
	int i = rand() % 3;   // 0부터 2 사이 숫자 반환

	// break 사용에 주의할 것!
	switch (i)
	{
		case 0: printf("가위!\n"); break;
		case 1: printf("바위!\n"); break;
		case 2: printf("보!\n"); break;
		default: printf("몰라요!\n");
	}

    return 0; 

}
```

#### 예제: 학생 구분

* 아래 코드 문제점: case가 너무 많음. 하지만, case와 break 활용 이해에 도움됨.

```c
#include <stdio.h>

int main(void) {
     /*
	초등학생(8-13)/중학생(14-16)/고등학생(17-19)/일반인으로 구분하기

	switch ... case ... 활용!
	*/
    
    int age = 18;

	switch (age)
	{
		case 8:
		case 9:
		case 10:
		case 11:
		case 12:
		case 13: printf("초등학생입니다.\n"); break;
		case 14:
		case 15:
		case 16: printf("중학생입니다.\n"); break;
		case 17:
		case 18:
		case 19: printf("고등학생입니다.\n"); break;
		default: printf("학생이 아닌가봐요.\n"); break;
	}
    return 0;

}
```

---

### Python 구현

* `switch ... case ...` 지원 없음.
* 하지만 사전 자료형(`dict`)을 이용하여 쉽게 구현 가능.

#### 사전 자료형 활용


```python
import random 
import time
import sys
 
secret = 0
count=0

# 현재 시간에 맞추어 무작위로 정수 생성 가능

# time 함수: 1970.01.01 이후 흐른 시간(ns 단위)
current_time = int(time.time())
# 현재 시간 기준으로 무작위수 생성 지정
random.seed(current_time)

# 0과 100 사이의 무작위 정수 지정
secret = random.randint(0, sys.maxsize)%3

cases = {
    0: "가위",
    1: "바위",
    2: "보"
}
print(cases[secret])
```

    보



```python
import random 
import time
import sys
 
secret = 0
count=0

# 현재 시간에 맞추어 무작위로 정수 생성 가능

# time 함수: 1970.01.01 이후 흐른 시간(ns 단위)
current_time = int(time.time())
# 현재 시간 기준으로 무작위수 생성 지정
random.seed(current_time)

# 0과 100 사이의 무작위 정수 지정
secret = random.randint(0, sys.maxsize)%4

cases = {
    0: "가위",
    1: "바위",
    2: "보"
}
print(cases.get(secret, "잘못 냈어요!"))
```

    가위


#### `defaultdict` 활용


```python
import random 
import time
import sys

from collections import defaultdict
 
secret = 0
count=0

# 현재 시간에 맞추어 무작위로 정수 생성 가능

# time 함수: 1970.01.01 이후 흐른 시간(ns 단위)
current_time = int(time.time())
# 현재 시간 기준으로 무작위수 생성 지정
random.seed(current_time)

# 0과 100 사이의 무작위 정수 지정
secret = random.randint(0, sys.maxsize)%4

cases = {
    0: "가위",
    1: "바위",
    2: "보"
}

default_cases = defaultdict(lambda: "잘못 냈어요!", cases)
print(default_cases[secret])
```

    가위


---

## (C 언어) 프로젝트: Up & Down

* 동영상: [(나도코딩 C) 4-6 프로젝트](https://www.youtube.com/watch?v=QEQtFN2m2G4&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=26&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9)

#### 숫자맞히기 UP&DOWN 프로그램

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
 
// Up and Down
 
int main()
{
	srand(time(NULL));           // 현재시간 기준으로 무작위성 지정
	int num = rand()% 100 + 1;   // 1 - 100 사이의 숫자
	int answer = 0;              // 정답
    int chance = 5;              // 남은 기회
 
    // 무한 반복문 실행
	// 1: 참, 0: 거짓
    while(1)
    {
		printf("남은 기회 %d 번\n", chance--);
        printf("숫자를 맞혀보세요 (1-100): ");
        scanf("%d", &answer);
 
        if(answer > num){
            printf("DOWN!\n\n");
        }
        else if(answer < num){
            printf("UP!\n\n");
        }
        else if(answer == num){
            printf("정답입니다!\n\n");
			break;
        }
		else
		{
			printf("알 수 없는 오류가 발생했어요.\n\n");
		}
 
        if(chance == 0)
		{
            printf("모든 기회를 다 사용하셨네요. 아쉽게 실패했습니다.\n");
            break;
        }
    }
     
    return 0;
}
```

---

### Python 구현


```python
##### UP and DOWN

import random 
import time
import sys
 
# 현재 시간에 맞추어 무작위로 정수 생성 가능

# time 함수: 1970.01.01 이후 흐른 시간(ns 단위)
current_time = int(time.time())
# 현재 시간 기준으로 무작위수 생성 지정
random.seed(current_time)

# 0과 100 사이의 무작위 정수 지정
# sys.maxsize: 사용 가능한 양의 정수 최댓값. 시스템마다 다를 수 있음.
num = random.randint(0, sys.maxsize)%100

chance=5

# 무한 반복문 실행
while(1):
    print("남은 기회:", chance)
    chance -= 1

    answer = int(input("숫자를 맞혀보세요(0-100): "))

    if answer > num: 
        print("DOWN!")
    elif answer < num:
        print("UP!")
    elif answer == num:
        print("정답입니다!")
        break
    else:
        print("알 수 없는 오류가 발생했어요.")

    if chance == 0:
        print("모든 기회를 다 사용하셨네요. 아쉽게 실패했습니다.")
        break
```

    남은 기회: 5
    숫자를 맞혀보세요(0-100): 50
    UP!
    남은 기회: 4
    숫자를 맞혀보세요(0-100): 75
    DOWN!
    남은 기회: 3
    숫자를 맞혀보세요(0-100): 62
    UP!
    남은 기회: 2
    숫자를 맞혀보세요(0-100): 68
    정답입니다!


---
