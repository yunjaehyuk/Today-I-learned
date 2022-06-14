algorithm concept.md  
**2. 그리디 & 구현**  

동전 최소로 나누기

```python
n = int(input())
array = [500, 100, 50, 10]
count = 0
for i in array:
    count += n // i
    n = n % i
print(count)
```

1이 될 떄까지

```python
N = int(input())
K = int(input())
count = 0
while N > 1:
    if N % K != 0:
        N -= 1
        count += 1
    else:
        N /= K
        count += 1
print(count)
```

나는 while문을 사용해 n이 1이 될떄까지 반복하는 while문을 사용하였다. N%K ! = 0인 경우와 아닌 경우를 구분해서 count횟수를 셌다.

## 구현

**구현이란**

머릿속에 있는 알고리즘을 소스코드로 바꾸는 과정이다.

**구현 유형의 문제**

풀이를 떠올리는 것은 쉽지만 소스코드로 옮기기 어려운 문제 

알고리즘 문제에서 2차원 공간은 행렬의 의미로 사용된다.

시뮬레이션 및 완전 탐색문제

2차원 공간에서 방향 벡터가 자주 활용된다. 

**방향벡터**

시뮬레이션 및 완전 탐색 문제에서 2차원 공간에서자주 활용된다.

direction x

direction y

```python
#동, 북,  서, 남

 dx = [0, -1, 0, 1]

dy = [1, 0, -1, 0]

#현재 위치

x, y = 2, 2

for i in range(4):

       # 다음 위치

       nx = x  + dx[i]

       ny = y + dy[i]

       print(nx, ny) // 2,2
```

**<문제> 상하좌우: 문제 설명**

```python
M = int(input())
move_list = map(int, input().split())
dx = [0, -1, 0, 3]
dy = [2, 0, 0, 0]
x, y = 1, 1
for i in range(4):
    nx = x + dx[i]
    ny = y + dy[i]
print(nx, ny)
```

15강: 구현 유형 문제 풀이

완전 탐색 문제 유형

가능한 경우의 수를 모두 검사해보는 탐색방법
