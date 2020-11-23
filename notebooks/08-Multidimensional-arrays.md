# 8장 다차원 배열

감사의 글: 유튜브 동영상 모음집 
[(나도코딩 C)](https://www.youtube.com/watch?v=dEykoFZkf5Y&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP)에서 
설명하는 코드를 활용합니다. 
강의동영상을 공개한 
[나도코딩](https://www.youtube.com/channel/UC7iAOLiALt2rtMVAWWl4pnw)님께 
감사드립니다.

## 핵심

* 다차원 배열 이해

## (C 언어) 동물 뒤집기(메모리 게임)

* 동영상: [(나도코딩 C) 8-1 동물 뒤집기](https://www.youtube.com/watch?v=4iswgYTDJkg&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=54)

### 게임 설명

* 카드를 뒤집어서 동일한 동물이 그려진 카드 두 장 선택하는 게임

---

## (C 언어) 다차원 배열 기본

* 동영상: [(나도코딩 C) 8-2 다차원 배열 기본](https://www.youtube.com/watch?v=tdXf0fto6GA&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=55)

* 1차원, 2차원, 3차원 배열 이해하기

---
```c
#include <stdio.h>

int main(){
	// 다차원 배열

	// 1차원 배열
	int arr[5];

	// { ㅁㅁㅁㅁㅁ }

	// 2차원 배열
	int arr2[2][5];     // 길이가 5인 배열이 두 개 있다는 의미로 이해됨.
                        // 보다 실용적으로는 2x5 모양의 행렬로 이해할 수 있음.
	// { 
	//   {ㅁㅁㅁㅁㅁ},
	//   {ㅁㅁㅁㅁㅁ},
    // }

	// 3차원 배열
	int arr3[3][2][5]; // 길이가 5인 배열 두 개를 포함한 배열이 3개 있다는 의미로 이해됨.
                       // 보다 실용적으로는 길이가 5인 배열을 항목으로 갖는 3x2 모양의 행렬로 이해 가능
                       // 이미지 픽셀을 다룰 때 보통 이렇게 사용됨.

	// { 
    //   { {ㅁㅁㅁㅁㅁ}, {ㅁㅁㅁㅁㅁ} },
    //   { {ㅁㅁㅁㅁㅁ}, {ㅁㅁㅁㅁㅁ} },
    //   { {ㅁㅁㅁㅁㅁ}, {ㅁㅁㅁㅁㅁ} } 
    // }

    return 0;
}
```

---

## (C 언어) 다차원 배열 접근

* 동영상: [(나도코딩 C) 8-3 다차원 배열 접근](https://www.youtube.com/watch?v=3SUa32DdMrI&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=56)

* 항목 접근은 차원에 맞는 좌표 이용 (아래 그림 참조)

* 3차원까지는 행렬 개념으로 이해하면 됨.

    ```c
    x1 = arr[2];        // 2번 인덱스 값
    x2 = arr2[0][5];    // 0번 행 5번 열 값
    x3 = arr3[2][1][3]; // 2번 행 1번 열의 3번 인덱스 값
    ```

---

## (C 언어) 다차원 배열 선언

* 동영상: [(나도코딩 C) 8-4 다차원 배열 선언](https://www.youtube.com/watch?v=DdW4-IsWa0U&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=57)

* 차원에 맞게 중괄호를 중첩으로 적용하여 선언

---
```c
#include <stdio.h>

int main(){
	// 다차원 배열

	// 1차원 배열
	int arr[5] = {1, 2, 3, 4, 5};

	// 2차원 배열
	int arr2[2][5] = {
		{1, 2, 3, 4, 5},
		{6, 7, 8, 9, 10}
	};

	// 3차원 배열
	int arr3[3][2][5] = {
        {{1, 2, 3, 4, 5},
		 {6, 7, 8, 9, 10}},
		{{1, 2, 3, 4, 5},
         {6, 7, 8, 9, 10}},
		{{1, 2, 3, 4, 5},
		 {6, 7, 8, 9, 10}}
	};

    return 0;
}
```

---

### Python 구현


```python
# 1차원 배열
arr = [1, 2, 3, 4, 5]
```


```python
# 2차원 배열
arr2 = [
        [1, 2, 3, 4, 5],
        [6, 7, 8, 9, 10]
       ]
```


```python
# 3차원 배열
arr3= [
        [[1, 2, 3, 4, 5],
         [6, 7, 8, 9, 10]],
        [[1, 2, 3, 4, 5],
         [6, 7, 8, 9, 10]],
        [[1, 2, 3, 4, 5],
         [6, 7, 8, 9, 10]]
      ]
```

* 넘파이(numpy) 모듈의 어레이(array)를 사용하면 보다 많은 정보를 쉽게 다룰 수 있음.


```python
import numpy as np

arr3_array = np.array(arr3)
```

* `arr3_array`는 어레이 자료형임.


```python
type(arr3_array)
```




    numpy.ndarray



* `shape` 속성에 차원 정보가 들어있음.


```python
arr3_array.shape
```




    (3, 2, 5)



---

## (C 언어) 다차원 배열 사용: 반복문 활용

* 동영상: [(나도코딩 C) 8-5 다차원 배열 사용](https://www.youtube.com/watch?v=N_v3MuuEikw&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=58)

* 차원에 따라 반복문의 중첩 정도가 달라짐.

#### 2차원 배열과 반복문

---
```c
#include <stdio.h>

int main(){
	// 다차원 배열

	// 2차원 배열
	int arr2[2][5] = {
		{1, 2, 3, 4, 5},
		{6, 7, 8, 9, 10}
	};

	printf("2차원 배열 항목 확인\n\n");
	for (int i = 0; i<2; i++)
	{
		for (int j = 0; j<5; j++)
		{
			printf("2차원 배열 (%d, %d)의 값: %d\n", i, j, arr2[i][j]);
		}
		printf("\n");
	}

    return 0;
}
```

---
```c
2차원 배열 항목 확인

2차원 배열 (0, 0)의 값: 1
2차원 배열 (0, 1)의 값: 2
2차원 배열 (0, 2)의 값: 3
2차원 배열 (0, 3)의 값: 4
2차원 배열 (0, 4)의 값: 5

2차원 배열 (1, 0)의 값: 6
2차원 배열 (1, 1)의 값: 7
2차원 배열 (1, 2)의 값: 8
2차원 배열 (1, 3)의 값: 9
2차원 배열 (1, 4)의 값: 10
```
---

#### 3차원 배열과 반복문

---
```c
#include <stdio.h>

int main(){
	// 다차원 배열

	// 3차원 배열
	int arr3[3][2][5] = {
		{
			{1, 2, 3, 4, 5},
			{6, 7, 8, 9, 10}
		},
		{
			{11, 12, 13, 14, 15},
			{16, 17, 18, 19, 20}
		},
		{
			{21, 22, 23, 24, 25},
			{26, 27, 28, 29, 30}
		}
	};

	printf("3차원 배열 항목 확인\n\n");
	for (int i = 0; i<3; i++)
	{
		for (int j = 0; j<2; j++)
		{
			for (int k = 0; k<5; k++)
			{
				printf("3차원 배열 (%d, %d, %d)의 값: %d\n", i, j, k, arr3[i][j][k]);
			}
			printf("\n");
		}
		printf("\n");
	}

    return 0;
}
```

---
```c
3차원 배열 항목 확인

3차원 배열 (0, 0, 0)의 값: 1
3차원 배열 (0, 0, 1)의 값: 2
3차원 배열 (0, 0, 2)의 값: 3
3차원 배열 (0, 0, 3)의 값: 4
3차원 배열 (0, 0, 4)의 값: 5

3차원 배열 (0, 1, 0)의 값: 6
3차원 배열 (0, 1, 1)의 값: 7
3차원 배열 (0, 1, 2)의 값: 8
3차원 배열 (0, 1, 3)의 값: 9
3차원 배열 (0, 1, 4)의 값: 10


3차원 배열 (1, 0, 0)의 값: 11
3차원 배열 (1, 0, 1)의 값: 12
3차원 배열 (1, 0, 2)의 값: 13
3차원 배열 (1, 0, 3)의 값: 14
3차원 배열 (1, 0, 4)의 값: 15

3차원 배열 (1, 1, 0)의 값: 16
3차원 배열 (1, 1, 1)의 값: 17
3차원 배열 (1, 1, 2)의 값: 18
3차원 배열 (1, 1, 3)의 값: 19
3차원 배열 (1, 1, 4)의 값: 20


3차원 배열 (2, 0, 0)의 값: 21
3차원 배열 (2, 0, 1)의 값: 22
3차원 배열 (2, 0, 2)의 값: 23
3차원 배열 (2, 0, 3)의 값: 24
3차원 배열 (2, 0, 4)의 값: 25

3차원 배열 (2, 1, 0)의 값: 26
3차원 배열 (2, 1, 1)의 값: 27
3차원 배열 (2, 1, 2)의 값: 28
3차원 배열 (2, 1, 3)의 값: 29
3차원 배열 (2, 1, 4)의 값: 30
```
---

---

### Python 구현

* 반복문 사용은 기본적으로 동일함.


```python
print("3차원 배열 항목 확인\n")

for i in range(3):
    for j in range(2):
        for k in range(5):
            print("3차원 배열 (%d, %d, %d)의 값: %d" % (i, j, k, arr3[i][j][k]))
    print()
```

    3차원 배열 항목 확인
    
    3차원 배열 (0, 0, 0)의 값: 1
    3차원 배열 (0, 0, 1)의 값: 2
    3차원 배열 (0, 0, 2)의 값: 3
    3차원 배열 (0, 0, 3)의 값: 4
    3차원 배열 (0, 0, 4)의 값: 5
    3차원 배열 (0, 1, 0)의 값: 6
    3차원 배열 (0, 1, 1)의 값: 7
    3차원 배열 (0, 1, 2)의 값: 8
    3차원 배열 (0, 1, 3)의 값: 9
    3차원 배열 (0, 1, 4)의 값: 10
    
    3차원 배열 (1, 0, 0)의 값: 1
    3차원 배열 (1, 0, 1)의 값: 2
    3차원 배열 (1, 0, 2)의 값: 3
    3차원 배열 (1, 0, 3)의 값: 4
    3차원 배열 (1, 0, 4)의 값: 5
    3차원 배열 (1, 1, 0)의 값: 6
    3차원 배열 (1, 1, 1)의 값: 7
    3차원 배열 (1, 1, 2)의 값: 8
    3차원 배열 (1, 1, 3)의 값: 9
    3차원 배열 (1, 1, 4)의 값: 10
    
    3차원 배열 (2, 0, 0)의 값: 1
    3차원 배열 (2, 0, 1)의 값: 2
    3차원 배열 (2, 0, 2)의 값: 3
    3차원 배열 (2, 0, 3)의 값: 4
    3차원 배열 (2, 0, 4)의 값: 5
    3차원 배열 (2, 1, 0)의 값: 6
    3차원 배열 (2, 1, 1)의 값: 7
    3차원 배열 (2, 1, 2)의 값: 8
    3차원 배열 (2, 1, 3)의 값: 9
    3차원 배열 (2, 1, 4)의 값: 10
    


---

## (C 언어) 프로젝트

* 동영상: [(나도코딩 C) 8-6 프로젝트(전반전)](https://www.youtube.com/watch?v=2Zxp1eCv2-M&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=59)
* 동영상: [(나도코딩 C) 8-7 프로젝트(후반전)](https://www.youtube.com/watch?v=_gjGH-ng2RI&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=60)
* 동영상: [(나도코딩 C) 8-8 프로젝트(연장전)](https://www.youtube.com/watch?v=romtC4SjzjM&list=PLMsa_0kAjjrdiwQykI8eb3H4IRxLTqCnP&index=61)

* 동물 뒤집기(메모리 게임)
    * 10마리의 서로 다른 동물 (동물 별로 두 장의 카드 사용)
    * 사용자로부터 2개의 입력값을 받아 같은 동물을 츶으면 카드 뒤집기
    * 총 실패 횟수 알려주기

---
```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int arrayAnimal[4][5]; // 카드 20장의 위치 지정
int checkAnimal[4][5]; // 뒤집혔는지 여부를 기억하는 배열. 항목이 0으로 자동 초기화됨.
char * strAnimal[10];  // 동물 이름들의 배열

void initAnimalArray();
void initAnimalName();
void shuffleAnimal();
int getEmptyPosition();
int conv_pos_x(int x);
int conv_pos_y(int y);
void printAnimals();
void printQuestion();
int foundAllAnimals();

int main()
{
	srand(time(NULL));

	initAnimalArray();
	initAnimalName();

	shuffleAnimal();

	int failCount = 0; // 실패 횟수 저장

	while(1)
	{
		int select1 = 0; // 사용자 선택 수 1
		int select2 = 0; // 사용자 선택 수 2
		
		printAnimals(); // 동물 위치 출력
		printQuestion(); // 문제 출력(카드 지도 보여주기)

		printf("뒤집을 카드 두 개를 고르세요: ");
		scanf("%d %d", &select1, &select2);

		if (select1 == select2)
			continue; 

		// 좌표를 확인한 다음에 동일한 동물인지 확인하기
		int firstSelect_x = conv_pos_x(select1);
		int firstSelect_y = conv_pos_y(select1);

		int secondSelect_x = conv_pos_x(select2);
		int secondSelect_y = conv_pos_y(select2);

		// 아직 뒤집히지 않은 카드이고 두 동물이 동일한지 여부확인
		if (
			checkAnimal[firstSelect_x][firstSelect_y] == 0
			&& checkAnimal[secondSelect_x][secondSelect_y] == 0
			&& arrayAnimal[firstSelect_x][firstSelect_y] 
				== arrayAnimal[secondSelect_x][secondSelect_y]
			)
		{
			printf("\n\n빙고! : %15s 발견\n\n", 
                    strAnimal[arrayAnimal[firstSelect_x][firstSelect_y]]);
			checkAnimal[firstSelect_x][firstSelect_y] = 1;
			checkAnimal[secondSelect_x][secondSelect_y] = 1;
		}
		else{
			printf("\n\n땡!! (틀렸거나 아미 뒤집힌 카드입니다!\n");
			printf("%d : %s\n", select1, 
                    strAnimal[arrayAnimal[firstSelect_x][firstSelect_y]]);
			printf("%d : %s\n", select2, 
                    strAnimal[arrayAnimal[secondSelect_x][secondSelect_y]]);
			printf("\n\n");
			
			failCount++;
		}

		// 모든 동물을 다 찾은 경우
		if (foundAllAnimals() == 1)
		{
			printf("\n\n축하합니다! 모든 동물을 다 찾았네요!\n");
			printf("지금까지 총 %d번 실수하였습니다.\n", failCount);
			break;
		}
	}

    return 0;
}

void initAnimalArray()
{
	for (int i=0; i < 4; i++) 
	{
		for (int j = 0; j < 5; j++)
		{
			arrayAnimal[i][j] = -1; // 카드 선정 초기화
		}
	}
}

void initAnimalName()
{
	strAnimal[0] = "원숭이";
	strAnimal[1] = "하마";
	strAnimal[2] = "강아지";
	strAnimal[3] = "고양이";
	strAnimal[4] = "돼지";

	strAnimal[5] = "코끼리";
	strAnimal[6] = "기린";
	strAnimal[7] = "낙타";
	strAnimal[8] = "타조";
	strAnimal[9] = "호랑이";
}

void shuffleAnimal()
{
	// 10마리의 동물을 2번씩 무작위로
	// 4x5 크기의 2차원 행렬에 위치시키기
	for (int i = 0; i<10; i++)
	{
		for (int j = 0; j<2; j++)
		{
			int pos = getEmptyPosition();
			int x = conv_pos_x(pos);
			int y = conv_pos_y(pos);

			arrayAnimal[x][y] = i;
		}
	}
}

int getEmptyPosition()
{
	// 4x5 크기의 행렬에서 빈 위치의 좌표 찾기
	while(1)
	{
		int randPos = rand() % 20; // 0-19 사이의 숫자 반환
		int x = conv_pos_x(randPos);
		int y = conv_pos_y(randPos);

		if (arrayAnimal[x][y] == -1)
		{
			return randPos;
		}
	}
	return 0;
}

int conv_pos_x(int x)
{
	// 4x5 크기의 2차원 배열에서 행의 값 확인
	return x / 5;
}

int conv_pos_y(int y)
{
	// 4x5 크기의 2차원 배열에서 열의 값 확인
	return y % 5;
}

void printAnimals()
{
	printf("\n=====쉿, 이건 비밀인데 몰래 보여주는 거임.=====\n\n");
	// 4x5 크기의 동물로 구성된 행렬 출력
	for (int i=0; i<4; i++)
	{
		for (int j=0; j<5; j++)
		{
			printf("%15s", strAnimal[arrayAnimal[i][j]]);
		}
		printf("\n");
	}
	printf("\n=======================================\n\n");
}

void printQuestion()
{ 
	printf("\n\n(문제)\n");

	int seq = 0;

	for (int i=0; i<4; i++)
	{
		for (int j=0; j<5; j++)
		{
			// 카드를 뒤집어서 정답을 맞혔으면 동물이름 보여주기
			if (checkAnimal[i][j] != 0)
			{
				printf("%15s", strAnimal[arrayAnimal[i][j]]);
			}
			// 정답을 맞히지 못했으면 위치를 나타내는 숫자 보여주기
			else{
				printf("%15d", seq);
			}
			seq++;
		}
		printf("\n");
	}
}

int foundAllAnimals()
{
	for (int i=0; i<4; i++)
	{
		for (int j=0; j<5; j++)
		{
			if (checkAnimal[i][j] == 0)
			{
				return 0;
			}
		}
	}

	// 모든 동물을 다 찾은 경우
	return 1;
}
```
---

---

### Python 구현


```python
import random 
import time
import sys
```

* `arrayAnimlal` 초기화 방법 1: 중첩 반복문 활용


```python
arrayAnimal = []
```


```python
def initAnimalArray():
    for _ in range(4):
        new = []
        for _ in range(5):
            new.append(-1)
        arrayAnimal.append(new)
```


```python
arrayAnimal
```




    []



* `arrayAnimlal` 초기화 방법 2: 리스트 조건제시법 활용
    * 참조: [리스트 조건제시법 이해](https://wikidocs.net/23200)


```python
arrayAnimal = [[-1 for j in range(5)] for i in range(4)]
```


```python
arrayAnimal
```




    [[-1, -1, -1, -1, -1],
     [-1, -1, -1, -1, -1],
     [-1, -1, -1, -1, -1],
     [-1, -1, -1, -1, -1]]



* 동물 리스트 지정


```python
strAnimal = ["원숭이", "하마", "강아지", "고양이", "돼지", "코끼리", "기린", "낙타", "타조", "호랑이"]
```

* 동물 리스트 지정(영어): 줄간격 맞추기가 보다 용이함.


```python
strAnimal = ["monkey", "hippo", "dog", "cat", "pig", 
             "elephant", "giraffe", "camel", "ostrich", "tiger"]
```

* 동물사진이 뒤집혀져있는가에 대한 정보를 담는 2차원 배열
    * 0: 아직 숨겨져 있음(기본값)
    * 1: 이미 뒤집혀져서 게임에서 제외됨 (빙고일 경우 1로 변경됨)
    
* 주의사항: 
    * C 언어 코드에서 `checkAnimal` 2차원 배열은 선언만 되었고 항목 초기화가 이루지 지지 않았음.
    * 하지만 C 언어 컴파일 과정에서 자동으로 모든 항목이 0으로 초기화됨. 
    * 참조: [PythonTutor: 배열 초기화](http://pythontutor.com/visualize.html#code=int%20checkAnimal%5B4%5D%5B5%5D%3B%20//%20%EB%92%A4%EC%A7%91%ED%98%94%EB%8A%94%EC%A7%80%20%EC%97%AC%EB%B6%80%EB%A5%BC%20%EA%B8%B0%EC%96%B5%ED%95%98%EB%8A%94%20%EB%B0%B0%EC%97%B4%0A%0Aint%20main%28%29%20%7B%0A%0A%20%20foundAllAnimals%28%29%3B%0A%20%20return%200%3B%0A%7D%0A%0Aint%20foundAllAnimals%28%29%0A%7B%0A%20%20%20%20for%20%28int%20i%3D0%3B%20i%3C4%3B%20i%2B%2B%29%0A%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20for%20%28int%20j%3D0%3B%20j%3C5%3B%20j%2B%2B%29%0A%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20if%20%28checkAnimal%5Bi%5D%5Bj%5D%20%3D%3D%200%29%0A%20%20%20%20%20%20%20%20%20%20%20%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20return%200%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%0A%20%20%20%20//%20%EB%AA%A8%EB%93%A0%20%EB%8F%99%EB%AC%BC%EC%9D%84%20%EB%8B%A4%20%EC%B0%BE%EC%9D%80%20%EA%B2%BD%EC%9A%B0%0A%20%20%20%20return%201%3B%0A%7D&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=c&rawInputLstJSON=%5B%5D&textReferences=false)

* 파이썬에서 배열 항목의 초기화는 자동으로 이루어지지 않음. 
    따라서 아래와 같이 직접 초기화 과정을 거쳐야 함.


```python
checkAnimal = [[0 for j in range(5)] for i in range(4)]
```


```python
checkAnimal
```




    [[0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0], [0, 0, 0, 0, 0]]



* `getEmptyPosition()` 함수 정의
    * C 언어 코드에서와는 달리 좌표 x, y를 직접 튜플로 반환할 수 있음.
    * C 언어에서 튜플은 기본 자료형이 아님. 
        하지만 다음 시간에 배울 구조체를 이용하여 구현할 수는 있음.


```python
def getEmptyPosition():
    current_time = int(time.time())
    random.seed(current_time)

    # 4x5 크기의 행렬에서 빈 위치의 좌표 찾기
    while True:
        randPos = random.randint(0, sys.maxsize) % 20 # 0-19 사이의 숫자 반환
        x = randPos // 5
        y = randPos % 5

        if (arrayAnimal[x][y] == -1):
            return x, y
```

* `conv_pos_x()`와 `conv_pos_y()` 두 함수는 그래도 여전히 유용함.


```python
def conv_pos_x(x):
    # 4x5 크기의 2차원 배열에서 행의 값 확인
    return x // 5
```


```python
def conv_pos_y(y):
    # 4x5 크기의 2차원 배열에서 행의 값 확인
    return y % 5
```

* `shuffleAnimal()`, `printAnimals()`, `printQuestion()`, `foundAllAnimals()` 
    네 함수는 동일하게 구현함.
* 파이썬의 `print()` 는 기본적으로 줄바꿈을 실행한다는 것에만 주의하면 됨.


```python
def shuffleAnimal():
    for i in range(10):
        for _ in range(2):
            x, y = getEmptyPosition()
            arrayAnimal[x][y] = i
```


```python
def printAnimals():
    print("\n=====쉿, 이건 비밀인데 몰래 보여주는 거임.=====\n")
    # 4x5 크기의 동물로 구성된 행렬 출력
    for i in range(4):
        for j in range(5):
            print("%10s" % strAnimal[arrayAnimal[i][j]], end=' ')
        print()

    print("\n=======================================\n")
```


```python
def printQuestion():
    print("\n\n(문제)")

    seq = 0

    for i in range(4):
        for j in range(5):
            # 카드를 뒤집어서 정답을 맞혔으면 동물이름 보여주기
            if (checkAnimal[i][j] != 0):
                print("%10s" % strAnimal[arrayAnimal[i][j]], end=' ')
            # 정답을 맞히지 못했으면 위치를 나타내는 숫자 보여주기
            else: 
                print("%10d" % seq, end=' ')

            seq += 1

        print("\n")

```


```python
def foundAllAnimals():
    for i in range(4):
        for j in range(5):
            if (checkAnimal[i][j] == 0):
                return 0

    # 모든 동물을 다 찾은 경우
    return 1
```

* `main()` 함수 본문 내용도 사실상 동일하게 구현 가능.
* `if __name__ == "__main__":` 로 감싸는 이유
    * 다른 코드로 import 될 때 실행되지 않도록 하기 위함임.
    * 현재 코드를 하나의 파이썬 파일로 작성한 후 직접 실행하면 실행되지만 
        다른 코드에 임포트되면 실행되지 않음. 
    * [리스트 조건제시법 이해](https://wikidocs.net/23200)에서도 C 언어 코드의 `main()` 함수와
        파이썬의 `if __name__ == "__main__":`의 활용예제를 찾아볼 수 있음.


```python
if __name__ == "__main__":
    arrayAnimal = [[-1 for j in range(5)] for i in range(4)]
    
    strAnimal = ["monkey", "hippo", "dog", "cat", "pig", 
                 "elephant", "giraffe", "camel", "ostrich", "tiger"]
    
    checkAnimal = [[0 for j in range(5)] for i in range(4)]
    
    shuffleAnimal()

    failCount = 0 # 실패 횟수 저장

    while True:
        printAnimals() # 동물 위치 출력
        printQuestion() # 문제 출력(카드 지도 보여주기)
        
        # 사용자에 의해 선택된 두 개의 수
        select1, select2 = map(int, input("뒤집을 카드 2 개를 고르세요: ").split())

        if (select1 == select2):
            continue

        # 좌표를 확인한 다음에 동일한 동물인지 확인하기
        firstSelect_x = conv_pos_x(select1)
        firstSelect_y = conv_pos_y(select1)

        secondSelect_x = conv_pos_x(select2)
        secondSelect_y = conv_pos_y(select2)

        # 아직 뒤집히지 않은 카드이고 두 동물이 동일한지 여부확인
        if ( (checkAnimal[firstSelect_x][firstSelect_y] == 0)
             and (checkAnimal[secondSelect_x][secondSelect_y] == 0)
             and (arrayAnimal[firstSelect_x][firstSelect_y] 
                 == arrayAnimal[secondSelect_x][secondSelect_y]) ):
            
            print("\n\n빙고!: %10s 발견\n" %
                    strAnimal[arrayAnimal[firstSelect_x][firstSelect_y]])
            
            checkAnimal[firstSelect_x][firstSelect_y] = 1
            checkAnimal[secondSelect_x][secondSelect_y] = 1
        else:
            print("\n\n땡!! (틀렸거나 아미 뒤집힌 카드입니다!\n")
            print("%d : %s\n" % (select1, strAnimal[arrayAnimal[firstSelect_x][firstSelect_y]]))
            print("%d : %s\n" % (select2, strAnimal[arrayAnimal[secondSelect_x][secondSelect_y]]))
            print("\n")

            failCount += 1

        # 모든 동물을 다 찾은 경우
        if (foundAllAnimals() == 1):
            print("\n\n축하합니다! 모든 동물을 다 찾았네요!\n")
            print("지금까지 총 %d번 실수하였습니다.\n" % failCount)
            break
```

    
    =====쉿, 이건 비밀인데 몰래 보여주는 거임.=====
    
      elephant        dog        dog    giraffe      camel 
           cat      camel      tiger    ostrich      tiger 
         hippo    ostrich     monkey        pig        pig 
        monkey    giraffe        cat   elephant      hippo 
    
    =======================================
    
    
    
    (문제)
             0          1          2          3          4 
    
             5          6          7          8          9 
    
            10         11         12         13         14 
    
            15         16         17         18         19 
    

