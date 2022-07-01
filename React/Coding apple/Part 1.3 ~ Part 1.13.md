## Part 1.3  JSX 문법 3가지

### **JSX**

Javascript에서 HTML파일을 쓸 수 있게 도와준다.

**JSX 문법1.**

class 넣을 땐 className을 쓴다.

**JSX 문법2.**

변수넣을 떈{중괄호}

**JSX 문법3.**

style 넣을 떈 style={{ 스타일명: “값”}}

font-size →fontSize로 적어야한다.

## Part 1.4 중요한 데이터는 변수말고 state에 담습니다.

return () 안에는 병렬로 태그 2개 이상 기입금지

React에서는 자료 잠깐 저장할 떈 state 써도 된다.

### state 만드는 법

```jsx
import { useState } from "react";

function App() {
let [a, b] = useState("남자 코트 추천");useState('남자 코트 추천');
}
```

1. import{useState} from “react”;
2. useState(보관할 자료)
3. let[작명,작명]

      앞에꺼 state에 보관했던 자료

      뒤에 꺼 state 변경도와주는 함수

### Destructring 문법

```jsx
let num = [1, 2];
  let [a, b] = [1, 2];
  // let a = num[0];
  // let b = num[1];
```

**Q1. 왜 state를 써야함?**

일반 변수는 갑자기 변경되면 html에 자동으로 반영안됨

state는 갑자기 변경되면 state쓰던 html은 자동 재랜더링 됨

**Q2. state 언제 써야함?**

변경시 자동으로 html에 반영되게 만들고 싶으면 state를 써야한다.

자주 변경될 것 같은 데이터들은 state에 저장했다가 html에 {데이터바인딩} 한다.

**숙제** 

글 목록 3개를 html 레이아웃을 잘 짜서 만들어온다. 제목부분에 들어갈 3개의 데이터는 state에 저장한 후 html에 집어넣는다.

## Part1.5 **버튼에 기능개발을 해보자 & 리액트 state변경하는 법**

**저번시간 숙제: 글제목 3개 만들기**

```jsx
let [글제목, a] = useState([
    "남자 코트 추천",
    "강남 우동맛집",
    "파이썬 독학",
  ]);
<h4>{글제목[0]}</h4>
        <p>2월17일 발행</p>
      </div>
      <div className="list">
        <h4>{글제목[1]}</h4>
        <p>2월 17일 발행</p>
      </div>
      <div className="list">
        <h4>{글제목[2]}</h4>
        <p>2월 17일 발행</p>
```

**워닝 메시지 끄기**

```jsx
/*eslint-disable*/
Lint 끄는 기능임

```

### 좋아요버튼 & 갯수 UI 만들기

**onClick 쓰는 법**

onClick={}안에 함수이름을 넣어야한다.

```jsx
<span onClick={() =>console.log(1);}}>👍</span>
```

**state 변경하는 법**

state 변경함수(새로운state)

```jsx
<h4>
{글제목[0]}
<span onClick={() => {{따봉변경(따봉 + 1);}}}>👍</span>{따봉}
</h4>
```

**숙제**

버튼누르면 첫 글이 ‘여자코드 추천’으로 바뀌는 기능만들기

## Part 1.6 **array, object state 변경하는 법**

**저번 시간 숙제 :글수정 버튼 만들기**

코드 스타일

```jsx
<button onClick={ ()=>{ 
      글제목변경(['여자코트 추천', '강남 우동맛집', '파이썬 독학'])
    } }> 수정버튼 </button>
```

프로그래머 스타일

```jsx
<button onClick={() => {
        let copy = [...글제목];
        copy[0] = '여자코트 추천'
        글제목변경(copy);
        }}>글수정
</button>
```

array의 X번쨰 항목 변경하고 싶으면 

array자료[X] = “바꿀값” 이렇게 하면된다.

### **state변경함수 동작원리**

**[state변경함수 특징]**

기존state == 신규state의 경우 변경안해줌

**[array/object 동작원리]**

```jsx
let arr = [1,2,3];
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/df3bba5a-2dec-424f-a520-87c5c420a49f/Untitled.png)

array/object 담은 변수엔 화살표만 저장된다.

[1,2,3]이 어딨는지 알려주는 화살표만 들어있음

let arr 변수엔 그 자료가 어디있는지 가리키는 화살표만 담겨있다.

```jsx
let copy = 글제목;
copy[0] = '여자코트 추천';
글제목변경(copy)
```

컴퓨터는 copy와 기존 글제목 state가 똑같다고 생각하기 때문에(화살표가 똑같아서) state를 변경안해준다.

```jsx
let copy = [...글제목];
copy[0] = '여자코트 추천';
글제목변경(copy)
```

이렇게 하면 화살표가 달라지는 문법이 된다.

[… 글제목]은 괄호를 벗겨져 독립적인 array 복사본을 생성해줄 수 있다.

**정리**

state가 array/object면 독립적 카피본을 만들어서 수정해야한다.

[...기존state]

{...기존state}

이렇게 하면 독립적인 카피가 하나 생성됩니다.

**숙제**

제목을 “가나다라”순으로 정렬하기

```jsx
<button onClick={() => {
    let copys = [...글제목]
    copys.sort()
    글제목변경(copys)

   }}> 가나다라순</button>
```

## Part 1.7 **Component : 많은 div들을 한 단어로 줄이고 싶으면**

**컴포넌트** 

한 단어로 축약한  것

긴 HTML을 한 단어로 깔끔하게 치환해서 넣을 수 있는 문법

**컴포넌트 만드는 법**

다른 function 바깥에 만들고 함수 이름은 대문자로 시작한다.

```jsx
<Modal></Modal>

</div>
function Modal() {
  return (
    <div className="modal">
       <h4>제목</h4>
       <p>날짜</p>
       <p>상세내용</p>
     </div>
  )
}
```

1.function 만들고

2.return() 안에 html 담기

3.<함수명></함수명> 쓰기

**Component는 언제 쓸까?**

1.반복적인 html 축약할 때

2.큰 페이지들

3.자주변경되는 것들

4.다른 페이지를 만들고 싶다면 

**컴포넌트의 단점:**

state 가져다쓸 떄 문제생김

## Part 1.8 **리액트 환경에서 동적인 UI 만드는 법 (모달창만들기)**

**모달 창**

사용자 인터페이스 디자인 개념에서 자식 윈도에서 부모 윈도로 돌아가기 전에 사용자의 상호동작을 요구하는 창을 말합니다.

**[동적인 UI 만드는 step]**

1. html css로 미리 디자인 완성
2. UI의 현재 상태를 state로 저장

state 하나 만들고

거기에 현재 UI의 상태정보를 저장해두라는 소리입니다.

```jsx
let [modal, setModal] = useState(false);
```

 3. state에 따라 UI가 어떻게 보일지 작성

JSX에서 조건문 쓰는 법

JSX 안에서는 if else 문법을 바로 사용할 수 없습니다. 삼항연사자만 JSX 중괄호 안에서 된다.

**삼항연산자(ternary operator)**

```jsx
조건식 ? 조건식 참일 때 실행할 코드 : 조건식 거짓일 때 실행할 코드
3 > 1 ? console.log('맞음') : console.log('아님')
```

```jsx
{
      modal == true ? <Modal></Modal> : null
}
```

리액트에서 UI만드는 과정을 비유하면

스위치와 전등만드는거랑 비슷하다고 보면 됩니다.

1. 일단 전등이쁘게 달아놓고
2. 스위치랑 연결하고
3. 스위치를 on으로 놓으면 불이 켜지고 off로 놓으면 불이 꺼지도록

만들어놓는 겁니다.

그리고 나중에 필요하면 스위치 조작만 하면 된다.

**숙제** 

제목을 또 누르면 모달창을 사라지게한다.

state인 modal 자체가 true/false의 갑을 저장하고 있다는 점을 활용하여 setModal() 함수 안에 modal을 넣었다. 

false일 떄는 true로, true일 떄는 false로 바뀌도록 느낌표를 바꾸었다.

글제목 클릭시

지금 state가 true면 setModal(false)

지금 state가 false면 setModal(true)

이런 코드를 실행하면 됩니다.

```jsx
<h4 onClick={()=>{setModal(!modal)}}>{글제목[2]}</h4>
```

false로 변경하는법

## Part 1.9 **map : 많은 div들을 반복문으로 줄이고 싶은 충동이 들 때**

**자바스크립트 map 함수 쓰는 법**

반복문으로 같은 html 반복생성하는 법

모든 array 자료 우측엔 map() 함수를 붙일 수 있다.


**map 함수**

1. array 자료 갯수만큼 함수안의 코드를 실행해줌
2. 함수의 파라미터는 array안에 있던 자료이다.
3. return 오른쪽에 있는걸 array로 담아준다.
**map 함수**

 1.   array 자료 갯수만큼 함수안의 코드를 실행해줌

```jsx
var 어레이 = [2,3,4];
어레이.map(function(){
  console.log(1)
});
```

2. 콜백함수에 파라미터 아무렇게나 작명하면 그 파라미터는 어레이 안에 있던 모든 자료를 하나씩 출력해준다.

```jsx
var 어레이 = [2,3,4];
어레이.map(function(a){
  console.log(a)
});
```

3. return 오른쪽에 있는걸 array로 담아준다.

## 유용한 파라미터 2개 사용가능

**매개변수(parameter)란** 

함수의 정의에서 전달받은 인수를 함수 내부로 전달하기 위해 사용하는 변수를 의미합니다.

**인수(argument)란** 

함수가 호출될 때 함수로 값을 전달해주는 값을 말합니다.

**근데 반복된 HTML에 각각 다른 제목을 부여하고 싶다면**
```
{ 
        글제목.map(function(a){
          return (
          <div className="list">
            <h4>{ a }</h4>
            <p>2월 18일 발행</p>
          </div> )
        }) 
      }
```
a라는 파라미터는 map이 반복될 떄마다 array자료 안에 있던 하나하나의 데이터들을 의미한다.

```
{
  글제목.map(function(a, i){
    return (<div className="list">
    <h4>{a}</h4>
    <p>2월 17일 발행</p>
  </div>)
  })
}
```

첫째 파라미터 a는 array안에 있던 자료

둘째 파라미터 i는 0부터 1씩 증가하는 정수

가 되어서 그렇습니다.

i 출력해보면 0 1 2 이런 식으로 나옵니다. 진짜임

**(참고) map 반복문으로 반복생성한 html엔 key={i} 이런 속성을 추가해야합니다.**

**결론**

비슷한 html 반복생성하려면 map()쓰면 된다.

**숙제**

지금 좋아요버튼을 누를 때 마다 모든 따봉갯수가 똑같이 1 증가하고 있습니다.

각각 개별적으로 증가하게 하려면 어떻게 해야할까요?

0번째 좋아요 버튼을 클릭시엔 따봉[0] + 1 을 해야하고

1번째 좋아요 버튼을 클릭시엔 따봉[1] + 1 을 해야하고

2번째 좋아요 버튼을 클릭시엔 따봉[2] + 1 을 해야하고

그러면 됩니다.

근데 따봉이라는건 state니까 state 변경함수 써야합니다. 그리고 array자료니까 array 자료변경시 주의점도 신경써야겠군요.

state가 array자료일 경우 복사부터 하고

그거 수정하면 된다고 해서 그렇게 했습니다.

array자료일 떄 인덱스 함수 사용하는것 조심하자

```jsx
<span onClick={()=>{ 
      let copy = [...따봉];
      copy[i] = copy[i] + 1;
      따봉변경(copy)  
   }}>👍</span> {따봉[i]}
```

## Part 1.10 **자식이 부모의 state 가져다쓰고 싶을 때는 props**

모달창안에 첫 번째 글제목을 넣어보자.

<Modal> 안에 글제목 state가 필요하데

자바스크립트에선 다른 함수에 있는 변수를 마음대로 가져다 쓸 수 없다. 그렇기 때문에 react에서는 props함수를 사용한다.

**prop로 부모 → 자식 state전송하는 법**

1. <자식컴포넌트 작명={state이름}>

```jsx
<Modal 글제목={글제목} </Modal>
```

1. props 파라미터 등록 후 props.작명 사용

```jsx
<h4 onClick={()=>{}}>{props.글제목[0]}</h4>
```

props 전송은 부모 → 자식만 가능하다.

**Q. 다양한 색의 모달창이 필요하다.**

파라미터문법은 다양한 기능을  하는 함수를 만들 떄 사용함.

props로 일반 문자도 전송가능

```jsx
<Modal color = {'yellow'} 글제목변경={글제목변경} 글제목={글제목}></Modal>
```

## Part 1.11 ****props를 응용한 상세페이지 만들기****

Q. 지금 누른 글 제목이 모달창안에 뜨게 하려면?

## Part 1.12 **input 1 : 사용자가 입력한 글 다루기**

<input>에 뭔가 입력시 코드실행하고 싶으면 onChange / onInput을 사용한다.

```jsx
<input onChange={() =>{}}/>
```

이벤트핸들러 매우 많음

검색해 씁시다.

**<input>에 입력한 값 가져오는 법**

```jsx
<input onChange={(e) =>{ console.log(e.target) }} /> 
```

e : 지금 발생하는 이벤트에 관련한 여러 기능이 담겨있음

target : 이벤트 발생한 html태그

e.target.value : input에 입력한 값

Q.왜 <span> 눌러도 모달창 뜸?

브라우저는 원래 그런식으로 동작한다.

상위 html로 퍼지는 이벤트버블링을 막고 싶으면

e.stopPropagtion()

내 상위요소로 클릭이 진행 되지 않는다.

<input>에 입력한 값 저장하려면

(정보) state변경함수는 늦게처리됨

숙제

버튼누르면 글 하나 추가되는 기능 만들기

힌트1. html 직접 하나 만들 필요없음

힌트2. array에 자료 추가하는 법은 구글에

숙제2

글마다 삭제버튼 & 기능 만들기

힌트 1. html 직접 지울 필요없음

            state 조작하면 됩니다. 

## Part 1.13 **class를 이용한 옛날 옛적 React 문법**

React 신문법을 쓰자
