### ****파이썬(Python) 문자열을 나누기 위한 split 구현하기****

### **1. 함수의 형태**

 split 의 파라미터 형태에 따라 다음과 같이 구분할 수 있습니다.

- 문자열.split() : 함수가 자동으로 띄워쓰기, 엔터 등을 인식해서 문자열을 나눈다.

```python
canvas = "can you go to the restoraut?"
print(canvas.split()) #['can', 'you', 'go', 'to', 'the', 'restoraut?']
```

- 문자열.split(‘구분자’) : 함수의 파라미터로 특정 구분자를 지정한다.

```python
canvas = "can, you, go?"
print(canvas) #can, you, go?
canvas_split = canvas.split(",")
print(canvas_split) #['can', ' you', ' go?']
```

- 문자열.split(‘구분자’, 분할횟수) : 두 번째 파라미터인 분할 횟수는 문자열을 자르는 횟수이다.

  

```python
canvas = "can, you, go, to, the, restoraut?"
print(canvas) #can, you, go, to, the, restoraut?
canvas_split = canvas.split(",",3)
print(canvas_split) #['can', ' you', ' go', ' to, the, restoraut?']
```

- 문자열.split(sep=’구분자’, maxsplit=분할횟수) : 파라미터에 변수를 지정한 형태이다. 바로 위의 함수와 같은 기능을 한다.
