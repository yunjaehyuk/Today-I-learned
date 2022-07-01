## Part 1.1 **강의 소개와 자바스크립트의 근본**

HTML 조작가능

```html
<h1 id="hello">안녕하세요</h1>

<script>
  document.getElementById('hello').innerHTML = '안녕';
</script>
```

**document** **->** 문서인데 여기선 html 웹문서겠죠

**마침표 ->** ~의

**getElementById('어쩌구')** **->** 아이디가 '어쩌구'인 html 요소 (일명 element) 를 찾으셈

**innerHTML ->** 딱봐도 그냥 내부 HTML이라는 뜻인듯

**= ->** 등호는 프로그래밍에서 오른쪽에 있는걸 왼쪽에 대입하라는 뜻입니다.

내부의 코드를 초록색으로 바꾸고 싶다.

```html
document.getElementById('hello').style.color = 'green';
```

.**getElementById()**는 셀렉터라고 부릅니다. html 요소를 찾기 위해 사용합니다.

**.innerHTML / .style / .color** 이렇게 점찍는데 괄호없는건 메소드(또는 함수) 라고 부릅니다.

html 요소의 어떤 속성을 변경할지 결정하기 위해 사용합니다.

html의 모든것을 바꿀 수 있다.

> **프로그래밍 하는 법**
> 

프로그래밍은 별거 아니고 컴퓨터에게 일시키는게 프로그래밍입니다.

코드를 막 짜서 컴퓨터에게 저거해라 이거해라 시키는겁니다.

**"너 저기가서 저것좀 바꿔"** 이게 아니라

**"너 id가 hello인 html요소 있지 그거 찾아서 안의 내용을 안녕으로 바꿔"**

## Part 1.2 **동적 UI 만드는 스텝 (Alert 박스 만들기)**

**UI 만드는 STEP**

1.HTML/CSS로 미리 디자인

2.필요할 떄 보여달라고 코드 짬

**Alert UI 디자인부터 하기**

```css
.alert-box {
  background-color: skyblue;
  padding: 20px;
  color: white;
  border-radius: 5px;
  display: none;
}
```

**버튼 누르면 Alert UI 보여주기**

onclick 안에 자바스크립립트를 실행시킬 수 있다.

```html
<button onclick="Alert 박스 보여주셈~~"> 버튼 </button>

<button onclick="document.getElementById('alert').display.style = 'block'";></button>
```

```html
<button onclick="document.getElementById('alert').style.display = 'none';"> 닫기 </button>
```

## Part 1.3 **자바스크립트 function 문법 사용법**

**자바스크립트 function 문법**

→ 긴 코드를 축약하고 싶을 떄 쓴다.

```css
function 자유롭게작명(){
  축약하고 싶은 긴 코드
}
```

**1. JS 코드는 밑에 짜야합니다**

**2.셀렉터 오타 주의**

어쩌구 of null

→ 대부분 셀렉터 오타

## Part 1.4 **function의 파라미터 문법**

**function에 사용가능한 파라미터 문법**

함수 내에 구멍 뚫었습니다.

구멍을 뚫는 법은

() 소괄호 내에 아무 글자나 적고

{} 중괄호 내에도 같은 글자 아무데나 적으면 됩니다.

구멍을 왜 뚫냐고요?

> 구멍을 뚫으면 함수를 업그레이드해서 사용할 수 있습니다. 구멍이 뚫려있으면 이제 함수를 쓸 때 그냥 쓰는게 아니라 소괄호 내에 뭔가 문자나 숫자등을 입력해서 사용가능합니다.

```jsx
function 알림창열기(구멍){
  document.getElementById('alert').style.display = 구멍;
}

알림창열기('none'); //이거 실행하면 알림창열릴듯
알림창열기('block');  //얘는 닫힐듯
```

**파라미터 작명은 여러개 가능**

```jsx
function 알림창열기(구멍,구멍2){
    document.getElementById('alert').style.display = 구멍
    document.getElementById('alert').innerHTML = 구멍2
  }
```

## Part 1.5 자바스크립트 이벤트리스너

**class찾기 가능**

getElementsByClassName()

```jsx
<p class="title1"> 테스트1 </p>
<p class="title1"> 테스트2 </p>
<script>
  document.getElementsByClassName('title1')[0].innerHTML = '안녕';
</script>
```

g**etElementsByClassName('클래스명')[순서]** 이렇게 쓰면 됩니다.

[0] 이렇게 순서를 넣는 이유는

getElementsByClassName 셀렉터는 일치하는 class가 들어있는 **모든** html 요소를 찾아주기 때문입니다.

> **이벤트 리스너**
> 

지금까진 버튼의 onclick=" " 안에 자바스크립트를 길게 짰는데 이것도 좀 더러워보입니다.

그게 보기싫으면 이벤트리스너 문법 사용하면 됩니다.

그럼 html 안에 자바스크립트 안적고도 똑같이 개발진행할 수 있습니다.

**더 배워볼 개념 1. event**

유저가 웹페이지 접속해서 클릭, 스크롤, 키보드입력, 드래그 등을 할 수 있는데 이걸 전문용어로 **이벤트**라고 부릅니다.

**2. 콜백함수**

파라미터자리에 들어가는 함수를 전문용어로 **'콜백함수'**라고 합니다.

콜백함수는 그냥 뭔가 순차적으로 실행하고 싶을 때 많이 보이는 함수형태이다.

## Part 1.6 **서브메뉴 만들어보기와 classList 다루기**

toggle : 껐다, 켰다 하다

CSS 짜기 귀찮아서 Bootstrap 라이브러리 

-버튼, -카드, -리스트 등……

bootstrap 홈페이지 가서 코드를 가져온다.

**Navbar 만들기**

**class 탈부착식으로**

```css
.list-group {
  display : none
}
.show {
  display : block
}
```

**버튼누르면 보여달라고 JS 짬**

class부착식으로 개발하면 

-애니메이션 추가 쉬움

-나중에 재사용 편리

**원하는 요소에 클래스 추가하기**

버튼 한 번 더 누르면 숨기기

```jsx
document.getElementsByClassName('navbar-toggler')[0].addEventListener('click', function(){
  document.getElementsByClassName('list-group')[0].classList.toggle('show');
});
```

.classList toggle()을  쓰면 

클래스명이 있으면 제거하고

없으면 붙여줍니다.

**편리한 querySelector( )** 

```jsx
document.querySelector('.list-group')
```

**다 찾아주는 querySelectorAll()**

```jsx
document.querySelectorAll('.list-group-item')[0]
```

.list-group-item에 해당하는 모든 요소를 다 찾아옴

(인덱스)

## Part 1.7 jQuery 사용법 간단정리

jQuery 설치

**jQuery 써서 html 변경하려면**

```html
<p class="hello">안녕</p>

<script>
  $('.hello').html('바보'); 
</script>
```

**jQuery 써서 스타일 변경하려면**

```html
<p class="hello">안녕</p>

<script>
  $('.hello').css('color', 'red');
</script>
```

**jQuery 써서 class 탈부착하려면** 

```html
<p class="hello">안녕</p>

<script>
  $('.hello').addClass('클래스명');
  $('.hello').removeClass('클래스명');
  $('.hello').toggleClass('클래스명');
</script>
```

toggleClass는 왔다갔다 토글해준다.

**html 여러개를 바꾸려면**

```html
<p class="hello">안녕</p>
<p class="hello">안녕</p>
<p class="hello">안녕</p>

<script>
  document.querySelectorAll('.hello')[0].innerHTML = '바보';
  document.querySelectorAll('.hello')[1].innerHTML = '바보';
  document.querySelectorAll('.hello')[2].innerHTML = '바보';
  $('.hello').html('바보');
</script>
```

그냥 자바스크립트는 저렇게 3줄 쓰면 됩니다.

$() 셀렉터는 그냥 querySelectorAll처럼 여러개가 있으면 전부 찾아줍니다.

그리고 거기에 [0] 이런 식으로 순서지정해줄 필요없이 냅다 .html() 붙이면

셀렉터로 찾은 모든 요소를 한 번에 조작하고 변경해줄 수 있습니다.

**이벤트리스너는**

```html
<p class="hello">안녕</p>
<button class="test-btn">버튼</button>

<script>
  $('.test-btn').on('click', function(){
    $('.hello').fadeOut();
  });
</script>
```

## Part 1.8 **모달창만들기와 간단한 애니메이션**

**UI 에 애니메이션 추가하려면**

가능한 CSS만으로 처리하는게 좋다.

## **  one-way UI 애니메이션 만드는 법

1. 시작스타일
2. 최종스타일

  3. 원할 떄 최종스타일로 변하라고 코드짬

  4.  transition 추가

## Part 1.9 **폼만들며 배워보는 if else**

**모달창 안에 form 만들기**

<form> 안의 <button> 주의

button의 type은 전송은 submit, 버튼은 button을 쓴다.

<form>은 서버로 유저정보 전송하려고 쓰는 것이다.

```html
<form action="success.html">
```

폼 전송시 이동할 페이지 기입란임

전송버튼 누를 떄 첫쨰 <input>에 입력된게 없으면 alert 띄우기

**숙제**

input에 입력한 값이 공백이면 알림창을 띄워라

## Part 1.10 공백검사 숙제와 elseif 문법

**전송버튼 누르면 공백체크하라던 숙제**

```jsx
$('form').on('submit', function(){
  if (input에 입력한 값이 공백) {
    alert('아이디 입력하쇼');
  }
});
```

input에 입력한 값을 찾는 방법

```jsx
var anText_sub1 = document.getElementById('info').value;
```

**폼전송 막으려면**

 e.preventDefault()

**오늘의 숙제 :**

1. 전송버튼 누를 때 아이디랑 패스워드 둘 다 공백검사하려면?

2. 전송버튼 누를 때 입력한 비번이 6자 미만이면 알림띄우기

```jsx
$('form').on('submit', function(e){
      if (document.getElementById('email1').value == ''){

        e.preventDefault();
        alert('아이디를 입력하시오.')
      }
      if (document.getElementById('email2').value == ''){
        e.preventDefault();
        alert('비번을 입력하시오.')
      }
      if(document.getElementById('email2').value.length < 6) {
        e.preventDefault();
        alert('비밀번호를 더 길게 입력하시오.')
      }
    });
```

