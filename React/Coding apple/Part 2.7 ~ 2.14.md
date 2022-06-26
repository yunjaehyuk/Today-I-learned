## Part 2.7 **리액트 라우터 3 : URL 파라미터로 상세페이지 100개 만들기**

**상세페이지에 상품명 표기하기**

데이터는 한 곳에서만 저장한다. 안그러면 여러 데이터 둘다 수정해야하기 때문이다.

props를 사용한다.

**비슷한 페이지 여러개 필요하면 url파라미터**

페이지 여러개 만들고 싶으면 :URL 파라미터를 쓴다.

```jsx
<Route path="/detail:id" element={<Detail shoes={shoes}/>
        }>
 </Route>
```

url 링크 주소는 [http://localhost:3000/detail0](http://localhost:3000/detail0)

[http://localhost:3000/detail](http://localhost:3000/detail0)1

로 변할 수 있다.

**Q. 페이지는 여러개인데 보이는 내용은 똑같다.**

각각 다른 컴포넌트를 100만개 만들던가

하나의 컴포넌트로 각각 다른 내용을 보여주던가

**useParams()**

유저가 URL파라미터에 입력한거 가져올려고 사용한다.

URL 파라미터 만들 떄 

여러개 가능

```jsx

```

### Q. 상품이 정렬되면?

-상세페이지 이상해진다.

오늘의 응용

/detail0 접속시 0번쨰 상품말고 상품id가 0인걸 보여주면 좋겠다.

## Part 2.8 **styled-components 쓰면 CSS 파일 없어도 되는데**

**styled-components 사용법**

Css파일 대신styled-components 쓰면 JS파일에서 전부 해결가능

```jsx
let YellowBtn = styled.button`
  background: yellow;
  color: black;
  padding: 10px;
`
function() {
...
<YellowBtn>버튼</YellowBtn>
...
}
```

장점1. CSS파일 안열어도 된다.

장점2. 스타일이 다른 js파일로 오염되지 않는다.

장점3. 페이지 로딩시간 단축

Q. 오렌지색 버튼이 필요하면?

props 문법을 쓴다.

props로 컴포넌트 재활용 가능

```jsx
let YellowBtn = styled.button`
  background: ${props => props.bg};
  color: black;
  padding: 10px;
`
function() {
...
<YellowBtn bg="blue" >버튼</YellowBtn>
...
}
```

참고1 간단한 프로그래밍 가능

글자색을 바꾸고 싶다.

```jsx
color: black ${props => props.bg == 'blue' ? 'white' : 'black'};
```

기존 스타일 복사가능

```jsx
let NewBtn = style.button(YellowBtn)
```

## Part 2.10 **Lifecycle과 useEffect 1**

useState는 JS파일마다 import해주어야 한다. 

### **컴포넌트의 Lifecycle**

1. 페이지에 장착되기도  하고(mount)
2. 업데이트도 되고(update)
3. 필요없으면 제거되고(unmount)

컴포넌트는 이런 인생주기를 겪음.

**컴포넌트의 인생을 배우는 이유**

는 중간중간 간섭가능

**인생에 간섭하는 방법**

"Detail 컴포넌트 등장 전에 이것좀 해줘"

"Detail 컴포넌트 사라지기 전에 이것좀 해줘"

"Detail 컴포넌트 업데이트 되고나서 이것좀 해줘"

이렇게 코드좀 실행해달라고 간섭할 수 있는데

간섭은 갈고리를 달아서 합니다.

**컴포넌트에 갈고리 다는 법**

```jsx
import {useState, useEffect} from 'react';

function Detail(){

  useEffect(()=>{
    //여기적은 코드는 컴포넌트 로드 & 업데이트 마다 실행됨
    console.log('안녕')
  });
  
  return (생략)
}

```

상단에서 useEffect import해오고

콜백함수 추가해서 안에 코드 적으면 이제 그 코드는 컴포넌트가 mount & update시 실행됩니다.

그래서 이게 Lifecycle hook 입니다.

**근데 useEffect 밖에 적어도 똑같은데요**

실은 useEffect 바깥에 적어도 똑같이 컴포넌트 mount & update시 실행됩니다.

컴포넌트가 mount & update시 function 안에 있는 코드도 다시 읽고 지나가서 그렇습니다.

**useEffect 쓰는 이유**

useEffect 안에 적은 코드는 html 렌더링 이후에 동작합니다. html 랜더링이 빠른  사이트를 원하면 쓸데없는 것들은 useEffect 안에 넣어본다.

```jsx
function Detail(){

  (반복문 10억번 돌리는 코드)
  return (생략)
}
// 반복문 돌리고 나서 html 코드 실행
function Detail(){

  useEffect(()=>{
    (반복문 10억번 돌리는 코드)
  });
  
  return (생략)
}
// html 코드 돌리고 나서 반복문 실행
```

useEffect 안에 있는 코드는 html 랜더링 후에 작동한다.

어려운 연산을 하기 위해서

서버에서 데이터 가져오는 작업

타이머 장착하기 위해서

**Q. 왜 이름이 Effect임?**

함수의 핵심기능과 상관없는 부가기능을 나타낸다.

**숙제**

Detail 페이지 방문 후 2초 지나면 <div>숨기기

(팁) 동적인 UI 어떻게 만들까?

**setTimeout**

자바스크립트로 X초 후에 코드를 실행하고 싶으면 사용한다.

```jsx
setTimeout( ()=>{  1초 후 실행할 코드 }, 1000);
```

## Part 2.11 **Lifecycle과 useEffect 2**

**숙제**

**동적 UI 만들기**

UI 상태 저장할 state 만들고

state에 따라서 UI가 어떻게 보일지 작성

**useEffect 실행조건 주기** 

useEffect 실행조건 넣을 수 있는 곳은 []

### **clean up function**

useEffect 동작 전에 실행되는 

return ()⇒ {}

**Q.그래서 타이머제거 어떻게 함?**

clearTimeout()

타이머제거 함수

clean up function은 mount시 실행안됨

unmount시 실행된다.

정리

```jsx
useEffect(()=>{ }) //재랜더링마다 코드를 실행하고 싶다.
useEffect(()=>{ },[]) // 2. mount시 1회 코드를 실행한다.
useEffect(()=>{
  return ()=> {

  }
 },[]) // 3. unmount시 1회 코드를 실행한다.

//4.useEffect 실행 전에 뭔가를 실행하고 싶으면 return() = >를 쓴다.
```

숙제 

모르겠다. 지금은

## Part 2.12 **리액트에서 서버와 통신하려면 ajax 1**

**AJAX 개념설명**

서버에 데이터를 요청한다.

**서버**

유저가 데이터달라고 요청을 하면 데이터를 보내주는 간단한 프로그램(네이버 웹툰, 유튜브)

데이터를 요청할 떄는 정확한 규격에 맞춰서 요청해야한다.

1. 어떤 데이터인지
2. 어떤 방법으로 요청할지(GET or POST)

잘 기재해야 데이터를 보내준다.

### **GET/POST 요청하는 법?**

**GET요청을 날리고 싶으면** 

가장 쉬운 방법은 브라우저 주소창입니다.

**POST요청을 날리고 싶으면**

<form action="요청할url" method="post"> 태그 이용

근데 GET, POST 요청을 저렇게 날리면 단점이 뭐냐면 **브라우저가 새로고침**
됩니다

### 

### **버튼만들기 & 누르면 AJAX 요청하기**

**AJAX란?**

서버에 GET, POST 요청을 할 때 **새로고침 없이** 데이터를 주고받을 수 있게 도와주는

간단한 브라우저 기능을 AJAX라고 합니다.

**ajax 쓰려면 옵션 3개 중 택 1**

1.XMLHttpRequest 

2.fetch()

3.axios 같은 거

axios 설치 

1. npm install axios
2. import axios from ‘axios’ 추가하기

```jsx

```

Q. ajax 요청 실패한 경우

```jsx
.catch(() => { })
```

숙제 

버튼을 누르면 서버에서 상품데이터 3개를 가져와서

메인페이지에 상품카드 3개를 더 생성해봅시다.

## Part 2.13 리액트에서 서버와 통신하려면 ajax 2: post, fetch

저번시간 숙제

데이터 가져와서 html로 보여주기

리액트) 스위치 조작함

shoes에 가져온 데이터를 추가한다.

**응용1. 버튼을 2번 누르면 7,8,9번 상품을 가져와서 html로 보여주려면?**

여기로 GET요청하면 7,8,9번 상품 줍니다.

https://codingapple1.github.io/shop/data3.json

버튼을 몇번 눌렀는지 어디 변수나 state 같은 곳에 기록해둬도 되겠군요.

**응용2. 버튼을 3번 누르면 더 상품이 없다고 안내문을 띄우려면?**

아니면 버튼을 숨기거나 그래도 되겠군요.

**응용3. 버튼을 누른 직후엔 "로딩중입니다" 이런 글자를 주변에 띄우고 싶으면?**

그리고 요청이 성공하거나 실패하거나 그 후엔 "로딩중입니다" 글자를 제거해야합니다.

### AJAX 추가 내용

서버로 데이터전송하는 POST요청

```jsx
axios.post('/safsd, {name : 'kim'})
```

**동시에 ajax 요청 여러개하면**

```jsx
Promise.all([[ axios.get('/url1'), axios.get('/url2')]])
.then(() =>{
  
})
```

### Part 2.14 **리액트에서 탭 UI 만들기**

버튼 3개와 박스 3개를 미리 만들어놓고 버튼 누를 때 마다 그에 맞는 박스 보여주는게 탭 UI입니다.

탭 UI 만들기

```jsx
<Nav variant="tabs"  defaultActiveKey="link0">
    <Nav.Item>
      <Nav.Link eventKey="link0">버튼0</Nav.Link>
    </Nav.Item>
    <Nav.Item>
      <Nav.Link eventKey="link1">버튼1</Nav.Link>
    </Nav.Item>
    <Nav.Item>
      <Nav.Link eventKey="link2">버튼2</Nav.Link>
    </Nav.Item>
</Nav>
<div>내용0</div>
<div>내용1</div>
<div>내용2</div>
```

defaultActiveKey=”link” 처음 웹사이트에 들어왔을 떄 눌러있는 버튼

3.state에 따라서  UI가 어떻게 보일지 작성

```jsx
<Nav variant="tabs"  defaultActiveKey="link0">
    <Nav.Item>
      <Nav.Link onClick={()=>{ 탭변경(0) }} eventKey="link0">버튼0</Nav.Link>
    </Nav.Item>
    <Nav.Item>
      <Nav.Link onClick={()=>{ 탭변경(1) }} eventKey="link1">버튼1</Nav.Link>
    </Nav.Item>
    <Nav.Item>
      <Nav.Link onClick={()=>{ 탭변경(2) }} eventKey="link2">버튼2</Nav.Link>
    </Nav.Item>
</Nav>
```

Q. 일반 if 조건문 쓰려면?

팁1 props. 어쩌구가 귀찮으면
