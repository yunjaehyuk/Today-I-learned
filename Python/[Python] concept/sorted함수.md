## 1.파이썬 정렬 sorted 함수 정리

**sorted(정렬할 데이터)**

**sorted(정렬할 데이터, reverse 파라미터)**

**sorted(정렬할 데이터, key 파라미터)**

**-key 옵션 (key 파라미터)**

sorted 함수의 key 파라미터는 어떤 것을 기준으로 정렬할 것인가? 에 대한 기준입니다

**-reverse 옵션(reverse 파라미터)**

해당 파라미터를 이용하면 오름차순으로 정렬할지 내림차순으로 정렬할지 정할 수 있습니다.
디폴트로는 reverse=False로 오름차순으로 정렬이 됩니다.

sorted(##, reverse = True)로 입력하게 되면 내림차순으로 정렬한다.

**리스트.sort()와 sorted(리스트)의 차이는?**

리스트.sort()는 본체의 리스트를 정렬해서 변환하느 것

sorted(리스트)는 정렬한 새로운 리스트를 반환하는 것

## 2.파이썬 정렬 sorted 함수 예제
```
a = [2, 4, 1, 9, 100, 29, 40, 10]
b = sorted(a)
c = sorted(a, reverse=True)
 
 
print(origin                  : {a})
print(sorted(a)               : {b}) 1,2,4…100
print(sorted(a, reverse=True) : {c}) 100,40,29…,1

```
