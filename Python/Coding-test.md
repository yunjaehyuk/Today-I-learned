## 1.algorithm.concept.md

### 1강:코딩테스트 개요 및 출제 경향

온라인 개발 환경 

replit

자신이 자주 사용하는 코드는 라이브러리화 하면 좋다.

### **IT 기업 코딩 테스트 최신 출제 경향**

**가장 빈도가 높은 알고리즘 유형**

- 그리디
- 구현
- DFS/BFS를 활용한 탐색

### 2강: 알고리즘 성능 평가

복잡도는 알고리즘의 성능을 나타내는 척도이다.

- **시간복잡도**: 특정한 크기의 입력에 대하여 알고리즘의 수행 시간 분석
- **공간 복잡도**: 특정한  크기의 입력에 대하여 알고리즘의 메모리 사용량 분석

동일한 기능을 수행하는 알고리즘이 있다면, 일반적으로 복잡도가 낮을수록 좋은 알고리즘이다.

### 빅오 표기법

가장 빠르게 증가하는 항만을 표기하는 표기법

함수의 상한만을 나타내게 된다.

예를 들어 연산횟수가 3N^3 + 5N^2가 있다면 

- 빅오 표기법에서는 차수가 가장 큰 항만 남기므로 O(N^3)으로 표현한다.

### 요구사항에 따라 적절한 알고리즘 설계하기

**시간제한(수행시간 요구사항)**

시간제한이 1초인 문제를 만났을 떄, 일반적인 기준은 다음과 같다..

N의 범위가 500인 경우: 시간 복잡도가 O(N^3)인 알고리즘을 설계하면 문제를 풀 수 있다.

N의 범위가 2000인 경우: 시간 복잡도가 O(N^2)인 알고리즘을 설계하면 문제를 풀 수 있다.

### 알고리즘 문제 해결 과정

1. 지문 읽기 및 컴퓨터적 사고
2. 요구사항(복잡도)
3. 문제 해결을 위한 아이디어 찾기
4. 소스코드 설계 및 코딩

### 10강 함수와 람다 표현식

함수란 특정한 작업을 하나의 단위로 묶어 놓은 것

**내장 함수**: 파이썬이 기본적으로 제공하는 함수

**사용자 정의 함수**: 개발자가 직접 정의하여 사용할 수 있는 함수

### 함수 정의하기

함수를 사용하면 소스코드의 길이를 줄일 수 있다.

- **매겨변수**: 함수 내부에서 사용할 변수
- **반환 값**: 함수에서 처리 된 결과를 반환

```python
def 함수명(매개변수):
    실행할 소스코드
    return 반환 값
```

```python
def add(A,B):
    return a + b

print(add(3,7))
```

### global 키워드

global 키워드로 변수를 지정하면 해당 함수에서는 지역 변수를 만들지 않고, 함수 바깥에 선언된 변수를 바로 참조하게 된다.

함수는 동일한 함수가 존재한다면 지역변수를 참조한다.

### 람다 표현식

람다 표현식을 이용하면 함수를 간단하게 작성할 수 있다.

- 특정한 기능을 수행하는 함수를 한 줄에 작성할 수 있다는 점이 특정이다.

```python
lambda 매개변수 : 표현식
```

add() 메서드

```python

def add(a,b):
    return a + b

print(add(3,7))
print((lambda a, b: a+b)(3,7))
```

```python
array = [('홍길동', 50),('이순신', 32), ('아무개', 74)]

def my_key(x):
    return x[1]

print(sorted(array, key=my_key))
print(sorted(array, key=lambda x: x[1]))
```

사용이유

함수를 간단히 하기 위해서

## 11강 자주 사용되는 표준 라이브러리

자주 사용되는 내장 함수

```python
# sum ()
result = sum([1,2,3,4,5])
print(result)

# min(), max()
min_result = min(7, 3, 5, 2)
max_result = max(7, 3, 5, 2)
print(min_result, max_result)

# eval()
result = eval("(3+5)*7")
print(result)

# sorted()
result = sorted([9, 1, 8, 5, 4])
reverse_result = sorted([9, 1, 8, 5, 4], reverse=True)
print(result)
print(reverse_result)
```

### 순열과 조합

모든 경우의 수를 고려해야 할 떄 어떤 라이브러리를 효과적으로 사용할 수 있을까요?

**순열**: 서로 다른 n개에서 서로 다른 r개를 선택하여 일렬로 나열하는 것

3! = 3 * 2 * 1

**조합**: 서로 다른 n개에서 순서에 상관 없이 서로 다른 r개를 선택하는 것  

3! / 3

```python
from itertools import permutations 
data = ['A', 'B', 'C']  #데이터 준비

result = list(permutations(data, 3))
print(result)

from itertools import combinations 
data = ['A', 'B', 'C']  #데이터 준비

result = list(combinations(data, 2))
print(result) // [('A', 'B'), ('A','C'), ('B','C')]
```

### Counter

내부의 원소가 몇 번씩 등장했는지를 알려준다.

### 최대 공약수와 최소 공배수

최대 공약수를 구해야 할 떄는 math 라이브러리의 gcd() 함수를 이용할 수 있습니다.

```
import math
# 최소 공배수를 구하는 함수
def lcm(a,b):
    return a * b // math.gcd(a,b)
a = 21
b = 14
print(math.gcd(21, 14))    #최대 공약수 계산
print(lcm(21,14))     #최소 공배수 계산
```




