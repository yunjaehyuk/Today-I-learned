## **innerText, innerHTML 사용법**

1. innerText vs innerHTML

innerText: 태그 안의 텍스트를 가져오거나 바꾸는 기능 (바뀌는 범위 : <태그>(텍스트)</태그> => 텍스트만 바뀜)

innerHTML : 태그 자체를 가져오거나 바꾸는 기능 (바뀌는 범위 : (<태그>텍스트</태그>) => 전체 다 바뀜)

```jsx
<script>
 console.log(document.getElementById('abc').innerText);
 console.log(document.getElementById('abc').innerHTML);
 // 안녕하세요 Hello world!
 // 안녕하세요 <span>Hello world!</span>

</script>
```

### 출처

innerText innerHTML

[https://redcow77.tistory.com/496](https://redcow77.tistory.com/496)
