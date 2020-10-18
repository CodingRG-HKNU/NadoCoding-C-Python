# 2장 변수, 상수, printf, scanf

## (C 언어) 정수형 변수

* 동영상: [(나도코딩 C) 2-2 정수형 변수](https://www.youtube.com/watch?v=pQjUGIeSr3k&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=5)

```c
#include <stdio.h>

int main(void) {
	int age = 12;        //자료형 명시
	printf("%d\n", age);

    // 변수에 할당된 값 수정 가능
	// 이미 선언된 변수는 자료형 명시하지 않음
	age = 13;            
	printf("%d\n", age);

	return 0;
}
```

---

### Python 구현

#### 주의사항

* Python의 `print`  함수는 줄바꿈을 자동으로 해줌. 
    따라서 굳이 줄바꿈 기호 `/n` 을 사용할 필요 없음.


```python
age = 12                # 변수의 자료형을 명시하지 않음
print("%d" % age)       # %d는 정수형 값을 받는 포맷 코드

# 변수에 할당된 값 수정 가능
# 심지어 자료형이 달려져도 됨
age = 'twelve'
print("%s" % age)       # 하지만 문자열을 받는 %s 포맷 코드를 사용해도 됨.
```

    12
    twelve


---

## (C 언어) 주석

* 동영상: [(나도코딩 C) 2-3 주석](https://www.youtube.com/watch?v=tqUVxNHeUys&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=6)

```c
#include <stdio.h>

int main(void) {
	// 여러 줄 주석은 /* ... */로 감싸야 함
    
    // 정수형 변수 예제
	/* int age = 12;        //자료형 명시
	printf("%d\n", age);
	// 변수는 수정 가능
	// 이미 선언된 변수는 자료형 명시하지 않음
	age = 13;            
	printf("%d\n", age); */

	// 한 줄 주석
	printf("1\n");
	// printf("2\n");   // 2는 주석처리됨
	printf("3\n");

	return 0;
}
```

---

### Python 구현


```python
# 정수형 변수 예제

# 여러 줄 주석은 세 개의 큰 따옴표(""")를 이용하여 감싸야 함

"""
age = 12                # 변수의 자료형을 명시하지 않음
print("%d" % age)       # %d는 정수형 값을 받는 포맷 코드

# 변수에 할당된 값 수정 가능
age = 13
print("%s" % age)       # 하지만 문자열을 받는 %s 포맷 코드를 사용해도 됨.
"""

# 한 줄 주석
print("1")
# print("2")   // 2는 주석처리됨.
print("3")
```

    1
    3


---

## (C 언어) 실수형 변수

* 동영상: [(나도코딩 C) 2-4 실수형 변수](https://www.youtube.com/watch?v=PtUCr7a1dPo&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=7)

```c
#include <stdio.h>

int main(void) {
	// 실수형 변수 예제
	float f = 46.5f;       // float 자료형 뒤에 f 붙혀줄 것
	printf("%f\n", f); 
	printf("%.2f\n", f);   // 소수점 자릿수 지정
	double d = 4.428;
	printf("%.3lf\n", d);
	printf("%lf\n", d); 

	return 0;
}
```

---

### Python 구현


```python
# 실수형 변수 예제

f = 46.5                    # 자료형과 f 기호를 명시할 필요 없음
print("%f" % f) 
print("%.2f" % f)           # 소수점 자릿수 지정

d = 4.428
print("%.3lf" % d)          # float 와 double 구분 없음
print("%lf" % d) 

# 문자열의 자릿수를 지정하고자 할 때  점 앞에 정수 지정
# 예를 들어 10자리수로 표현하고자 할 때 
# 주의: 자릿수는 소수점과 소수점 이하 숫자도 포함
pi = 3.14
print("%10.3f" % pi)

# 빈자리를 0으로 채울 수 있음
print("%010.3f" % pi)
```

    46.500000
    46.50
    4.428
    4.428000
         3.140
    000003.140


---

## (C 언어) 상수

* 동영상: [(나도코딩 C) 2-5 상수](https://www.youtube.com/watch?v=D4rZ7ZxxgAo&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=8)

```c
#include <stdio.h>

int main(void) {
	// 상수: const 라는 지정자 사용!
	const int YEAR = 2000;
	printf("태어난 년도: %d\n", YEAR);

	// 상수 수정은 오류 발생시킴
	// YEAR = 2001;

	return 0;
}
```

---

### Python 구현

* Python은 상수 지원 없음.

---

## (C 언어) 출력하기: printf

* 동영상: [(나도코딩 C) 2-6 printf](https://www.youtube.com/watch?v=wc3zH04hgBo&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=9)

```c
#include <stdio.h>

int main(void) {
	// 연산
	
	int add = 3 + 7;               // 10 (계산된 후에 저장됨)
	printf("3 + 7 = %d\n", add);

	// %d의 반복 횟수만큼 정수를 지정해야 함.
	printf("%d + %d = %d\n", 30, 79, 30 + 79);
	printf("%d * %d = %d\n", 30, 79, 30 * 79);
	
	return 0;
}
```

---

### Python 구현


```python
# 연산

add = 3 + 7                             # 10 (계산된 후에 저장됨)
print("3 + 7 = %d" % add)

# 문자열의 여러 곳에 값을 지정하기 위해 포맷 기호 여러 개 사용 가능

# %d의 반복 횟수만큼 정수를 지정해야 함.
print("%d + %d = %d" % (30, 79, 30 + 79))
print("%d * %d = %d" % (30, 79, 30 * 79))
```

    3 + 7 = 10
    30 + 79 = 109
    30 * 79 = 2370


---

## (C 언어) 값 입력받기: scanf

* 동영상: [(나도코딩 C) 2-7 scanf](https://www.youtube.com/watch?v=neFzhsdzI0Q&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=10)

#### 주의사항: scanf_s

* 동영상에서 사용되는 `scanf_s`는 Visual Studio이 사용하는 컴파일에서만 사용될 수 있음.
* 다양한 종류의 컴파일러 사용되고 있음.
* 대부분의 온라인 서버는 gcc 컴파일러 사용하며 `scanf_s`를 지원하지 않음.
* 그럴 때는 `scanf`를 대신 사용하면 됨.
* `scanf_s` 관련 자세한 설명: [scanf_s 사용하기](https://pang2h.tistory.com/200) 참조

#### 주의사항: 앰퍼샌드(&) 사용 여부

* 정수, 실수, 문자 등을 입력받는 변수에 `&`(앰퍼샌드) 기호를 붙혀서 사용함에 주의
* 문자열을 입력받는 변수에는 `&` 기호 사용하지 않음.

### (C 언어) 값 하나 입력받기

```c
#include <stdio.h>

int main(void) {
	// scanf
	// 키보드 입력을 받아서 저장
	int input;
	printf("값을 입력하세요: ");
	scanf("%d", &input);
	printf("입력값: %d\n", input);

	return 0;
}
```

---

### Python 구현

* `input` 함수가 키보드 입력을 받아서 되돌려 줌.
* `input` 함수의 인자로 문자열을 지정하여 어떤 값을 입력해야 하는지 정보 제공할 수 있음.
* 따라서 `print` 함수를 미리 사용할 필요 없음.


```python
# 키보드 입력받기 함수: input
# 따라서 동일한 이름의 변수를 사용하지 말아야 함.

# 입력 받은 값을 저장할 변수를 미리 선언할 필요 없음
input_value = input("값을 입력하세요: ")

print("입력값: %s" % input_value)
```

    값을 입력하세요: twelve
    입력값: twelve


#### 주의사항

* `input` 함수가 되돌려주는 값(리턴값)은 항상 문자열 자료형임.
* 따라서 아래와 같이 `%d`를 사용하면 오류 발생

* 숫자 12를 입력하더라도 문자열 `"12"`로 인식됨. 
    반면에 `%d`는 정수를 기대함. 따라서 오류 발생.


```python
input_value = input("값을 입력하세요: ")

print("입력값: %d" % input_value)
```

    값을 입력하세요: 12



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-6-3044794b98ce> in <module>
          1 input_value = input("값을 입력하세요: ")
          2 
    ----> 3 print("입력값: %d" % input_value)
    

    TypeError: %d format: a number is required, not str


---

### (C 언어) 여러 값 입력받기

* 여러 개의 값을 입력할 때 스페이스(space)를 분리 기준으로 사용

```c
#include <stdio.h>

int main(void) {
	// 여러 개의 값을 입력받기
	int one, two, three;
    printf("3개의 정수를 입력하세요: \n");
    scanf("%d %d %d", &one, &two, &three);
    printf("첫번째 값: %d\n", one);
    printf("두번째 값: %d\n", two);
    printf("세번째 값: %d\n", three);

	return 0;
}
```

---

### Python 구현

* Python은 여러 개의 값을 입력 받더라도 하나의 문자열로 처리함.
* 따라서 스페이스로 구분된 여러 개의 문자열을 스페이스를 기준으로 쪼개서 여러 개의 변수에 할당해야 함.


```python
# 여러 개의 값을 입력받기

three_ints = input("3개의 정수를 입력하세요: ")

one, two, three = three_ints.split()

print("첫번째 값: %s" % one)
print("두번째 값: %s" % two)
print("세번째 값: %s" % three)
```

    3개의 정수를 입력하세요: 3 12 789
    첫번째 값: 3
    두번째 값: 12
    세번째 값: 789


#### 주의사항

* 입력된 값은 모두 문자열로 처리한다. 따라서 `%s` 대신에  `%d`를 사용하면 오류 발생.
* 하지만 입력된 문자열이 모두 숫자로만 구성되었다면  
    `int` 함수를 이용하여 정수형으로 형변환을 한 후에 `%d`사용 가능


```python
# 여러 개의 값을 입력받기

three_ints = input("3개의 정수를 입력하세요: ")

one, two, three = three_ints.split()

print("첫번째 값: %d" % int(one))
print("두번째 값: %d" % int(two))
print("세번째 값: %d" % int(three))
```

    3개의 정수를 입력하세요: 3 12 789
    첫번째 값: 3
    두번째 값: 12
    세번째 값: 789


#### 주의사항

* `int` 함수를 `three_ints` 에 적용하면 오류 발생할 수 있음. 
* 이유는 `3 5 7`처럼 스페이스로 구분하면 해당 문자열은 더 이상 정수형 자료형이 아니기 때문임.

---

## (C 언어) 문자와 문자열 입력받기

* 문자열은 여러 개의 문자를 의미함
* `char`: 문자 자료형
    * 문자를 작은따옴표로 감쌈
    
* 문자열 자료형
    * 변수명에 문자열의 길이를 지정하는 형식으로 선언됨.
    * 즉, 문자들의 배열로 정의됨.
    * 문자열을 큰따옴표포 감쌈

### 문자 입력받기

```c
#include <stdio.h>

int main(void) {
	// 문자(한 글자), 
    char c = 'A';
    printf("c: %c\n", c);

    char d;
    scanf("%c", &d);
    printf("d: %c\n", d);

    return 0;
}
```

### 문자열 입력받기

```c
#include <stdio.h>

int main(void) {
	// 문자열(한 글자 이상의 여러 글자)
    // 문자열의 길이 지정 필요
    // 즉, 문자들의 배열(array) 자료형에 해당
    char str[256];
    
    // 문자열을 입력받을 때 & 기호 사용하지 않음
    // sizeof 함수는 지정된 배열의 크기 확인해줌
    scanf("%s", str, sizeof(str));
    printf("%s\n", str);

    return 0;
}
```

---

### Python 구현

* Python은 문자열 자료형만 사용.
* 문자는 길이가 1인 문자열에 해당함.
* 문자열 입력은 `input` 함수가 담당.
* `input` 함수는 키보드를 사용하여 Enter 키가 눌리기 전까지 입력된 모든 문자를
    하나의 문자열로 되돌려줌.


```python
string = input("문자열을 입력하세요: ")
print("입력된 문자열: %s" % string)
```

    문자열을 입력하세요: Learning C with Python!
    입력된 문자열: Learning C with Python!


#### 주의사항

* `str` 은 Python에서 문자열 자료형을 가리키는 지정자임. 따라서 변수 이름으로 사용하면 안됨.
* 여기서는 대신에 `string`을 변수 이름으로 사용함.
* Python에서는 문자열의 길이를 미리 지정해서 제한하지 않음.

---

## (C 언어) 프로젝트

* 동영상: [(나도코딩 C) 2-8 프로젝트](https://www.youtube.com/watch?v=Ca_UCG40JX0&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=11)

```c
#include <stdio.h>

int main(void) {
	// 프로젝트
    
	// 경찰관이 범죄자의 정보를 입수 (조서 작성)
	// 이름? 나이? 몸무게? 키? 범죄명?
	
	char name[256];
	printf("이름이 뭐에요? ");
	scanf("%s", name, sizeof(name));
	
	int age;
	printf("몇 살이에요? ");
	scanf("%d", &age);

	float weight;
	printf("몸무게는 몇 kg이에요? ");
	scanf("%f", &weight);

	double height;
	printf("키는 몇 cm이에요? ");
	scanf("%lf", &height);
	
	char what[256];
	printf("무슨 범죄를 저질렀어요? ");
	scanf("%s", what, sizeof(what));
	
	// 조서 내용 출력
	
	printf("\n\n--- 범죄자 정보 ---\n\n");
	printf(" 이름    : %s\n", name);
	printf(" 나이    : %d\n", age);
	printf(" 몸무게  : %.2f\n", weight);
	printf(" 키      : %.2lf\n", height);
	printf(" 범죄    : %s\n", what);
	
	return 0;
}

```

---

### Python 구현


```python
# 경찰관이 범죄자의 정보를 입수 (조서 작성)
# 이름? 나이? 몸무게? 키? 범죄명?

name = input("이름이 뭐에요? ")
age = input("몇 살이에요? ")
weight = input("몸무게는 몇 kg이에요? ")
height = input("키는 몇 cm이에요? ")
what = input("무슨 범죄를 저질렀어요? ")

# 조서 내용 출력

print("\n--- 범죄자 정보 ---\n")
print(" 이름     : %s" % name)
print(" 나이     : %d" % int(age))
print(" 몸무게  : %.2f" % int(weight))
print(" 키         : %.2lf" % int(height))
print(" 범죄      : %s" % what)
```

    이름이 뭐에요? 장발장
    몇 살이에요? 34
    몸무게는 몇 kg이에요? 56
    키는 몇 cm이에요? 178
    무슨 범죄를 저질렀어요? 빵훔치기
    
    --- 범죄자 정보 ---
    
     이름     : 장발장
     나이     : 34
     몸무게  : 56.00
     키         : 178.00
     범죄      : 빵훔치기


---
