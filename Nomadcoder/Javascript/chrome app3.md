2.16 Recap
= --> value를 할당
=== --> 같은지 확인
!== --> 같지 않음을 확인
#3.0 The Document Object
document는 브라우저에 이미 존재하는object이다.
document는 javascript가 html에 접근할 수 있는 방법이다.
Javascript로 html의 문서를 가져올 수 있을 뿐만 아니라 문서의 내용을 변경할 수 있다.
log 함수로 document.body 객체를 출력하면 태그내용이 나오고 dir 함수로 document.body 객체를 출력하면 객체의 속성이 출력된다.
dir은 객체의 속성을 확인하고, log는 객체의 요소를 확인하는 거군요.
3.1 HTML in Javascript
Javascript가 HTML의 id에 접근 하는 방법
텍스트를 변경하는 방법
클래스이름을 출력하는 방법
const title = document.getElementById("title");
title.innerText = "Got you!";
console.log(title);
console.log(title.className);
getElementById란 함수를 통해 id로 element의 요소를 가져올 수 있다.
3.2 Searching For Elements
HTML의 element id를 찾는다면 element의 모든 것을 가져올 수 있다.
Uncaught TypeError: Cannot set properties of null (setting 'innerText')
title을 찾을 수가 없어서 null이 출력된다.
getElementById >> 하나의 값
getElementsByClassName >> 배열 
많은 element를 가져올때 씀(array를 반환)
getElementsByTagName . . . >> 배열
위에서 id 빼고는 배열을 가져오기 때문에 title.innerText 와 같은 방법은 사용할 수 없다.
const title = document.querySelectorAll(".hello h1");
console.log(title);
querySelecot은 배열 대신에 하나의 요소만 가져다 준다.
querySelectorAll은 이 selector 안의 조건에 부합하는 모든 element를 가져다 준다.
또 Grab me3처럼 Id를 가진 태그의 하위 태그를 선택하고 싶을 때 위의 방법으로는 한계가 있다.
이때 사용하는 게 querySelector/querySelectorAll
const title = document.querySelector(".hellos h1"); 와 같이 쓰면
.hellos h1 마치 css 선택자 처럼 원하는 요소를 선택 가능
console.log((title.innerText = "히힛")); 화면에 글자가 히힛으로 바뀐다
3.3 Events
h1 의 style을 Javascript로 변경할 수 있다.
title.style.color = "blue";
eventListener는 말 그대로, event를 listen하는 거다.
addEventListener를 호출하고, listen하고 싶은 event이름을 알려줄거야.
title.addEventListener("click", handleTitleClick);
지금 js파일이 있기 때문에 js를 통해 html의 내용을 가져올 수 있는 거임
document가 html이 js파일을 load하기 때문에 존재 → 그 다음에 browser가 우리가 document에 접근할 수 있게 해줌
element의 내부를 보고 싶으면 console.dir()
기본적으로 object로 표시한 element를 보여줌(전부 js object임)
그 element 중 앞에 on이 붙은 것들은 event임
event: 어떤 행위를 하는 것
모든 event는 js가 listen할 수 있음
eventListener : event를 listen함 → js에게 무슨 event를 listen하고 싶은 지 알려줘야 함
title.addEventListener("click") : 누군가가 title을 click하는 것을 listen할 거임 → 무언가를 해줘야함
const title = document.querySelector("div.hello:first-child h1");

function handleTitleClick(){
console.log("title was clicked!");
}
title.addEventListener("click",handleTitleClick);

//click하면 handleTitleClick이라는 function이 동작하길 원함

//그래서 handle~ 함수에 () 를 안넣은 것임

//즉, js가 대신 실행시켜주길 바라는 것임!
}
클릭하는 행동을 들었을 떄 console.log(”title was clicked”) 를 출력한다.
function이 js에게 넘겨주고 유저가 title을 click할 경우에 js가 실행버튼을 대신 눌러주길 바라는 것임( 직접 handleTitleClick(); 이렇게 하는 것이 아니라)
함수에서 () 이 두 괄호를 추가함으로써 실행버튼을 누를 수 있는 거임
3.4 Events part Two
listen하고 싶은 event를 찾는 가장 좋은 방법은, 구글에 찾고 싶은 element의 이름, 예를들어 h1 html element mdn을 검색.
우리는 javascript의 element를 원하니, 링크에 Web APIs라는 문장이 포함된 페이지를 찾아. 왜냐면 이건 JS관점의 HTML Heading Element란 의미야.
너무 복잡하면 element를 console.dir로 출력해서 on~ 이라고 적혀있는걸 사용하면 됨.
function handleMouseEnter() {

title.innerText = "Mouse is here!"

}

function handleMouseLeave() {

title.innerText = "Mouse is gone!"

}

title.addEventListener("mouseenter", handleMouseEnter);

title.addEventListener("mouseleave", handleMouseLeave);
3.5 More Events
body만 document.body로 가져올 수 있다.
document의 body,head,title 이런것들은 중요하기 때문에
document.body.style~의 명령이 허용되지만, div같은것들은 호출이 안됨
나머지 element들은 querySelector getElementById로 불러와야됨
window는 기본제공
function handleWindowResize(){
document.body.style.backgroundColor = “tomato”;
}
function handleWindowCopy(){
alert(“copier”);
}

window.addEventListener(“resize”, handleWindowResize);
window.addEventListener(“copy”, handleWindowCopy);
3.6 CSS in Javascript
h1을 클릭할 때마다 색깔이 토마토, 블루로 변경하는 방법
const h1 = document.querySelector(".hello:first-child h1");
function handleTitleClick() {
  const currentColor = h1.style.color;
  let newColor;
  if (currentColor === "blue") {
    newColor = "tomato ";
  } else {
    newColor = "blue";
  }
  h1.style.color = newColor;
}

h1.addEventListener("click", handleTitleClick);
1.currentColor는 getter로써, 최근 color값을 복사하는 역할을 합니다. 그렇기에 의미론적으로 봤을 때 const로 선언하는 것이 적절합니다.
2. newColor는 setter로써, 변수에 대입된 색상값을 h1.style.color에 최종적으로 할당하는 역할을 합니다. 그리고 이것도 의미론적으로 봤을 때 값이 변경될 수 있다는 것을 염두에 두기 위해 let으로 선언하는 것이 적절합니다.
3. 다들 아시겠지만 프로그래밍언어에서 "="(equal) 표시는 오른쪽에 있는 값을 왼쪽에 대입한다는 뜻입니다. 이를 염두에 두시면 코드를 이해하는데 편하실 것 같습니다.
4. (참고) 함수 내에서 선언된 변수는 함수 밖에서는 존재하지 않습니다. 그렇기 때문에 const currentColor로 변수 선언을 하더라도, 함수가 호출될 때 마다 새로운 값을 받을 수 있습니다.
이를 토대로 코드를 순차적으로 이해하면,
1) click event 발생 및 함수 실행
2) currentColor 변수 선언 후 h1.style.color 값 복사 (getter)
3) newColor 변수 선언
4) currentColor 현재 값 확인
5) 조건에 따라 newColor에 "tomato" or "blue" 값 대입
6) 마지막으로 h1.style.color에 newColor값 대입 (setter)
변수를 2개를 쓰는 것은 원래 어떤 색이었는지'와 '새로 적용해줘야 할 색이 무엇인지'처럼 의미의 차이가 확연한 경우 다른 변수로 저장해두기 위해서이다.
3.7 CSS in Javascript part Two
const h1 = document.querySelector(".hello h1");
function handlieTitleClick() {
  const clickedClass = "clicked";

  if (h1.className === clickedClass) {
    h1.className = "";
  } else {
    h1.className = clickedClass;
  }
}
h1.addEventListener("click", handlieTitleClick);
1. style에 적합한 도구는 CSS, animation에 적합한 도구는 JS 이다
2. raw string이 반복되면 const로 만들어 준다
그냥 내가 만든 class 이름을 적으면 error의 위험이 있다.
스펠링을 잘못 적어도 뭐가 잘못 되었는지 모를 수 있기 때문.
const clickedClass = "clicked" 이렇게 적어야 된다.
변수를 생성하면 이 변수를 적는데 실수한다면, 자바스크립트는 이 변수가 정의되어 있지 않다고 알려줄 것이기 때문에 오류를 줄일 수 있음.
3.8 CSS in Javascript part Three
classList는 class들의 목록으로 작업할 수 있게 한다.
className은 이전calss를 상관하지않고 모든걸 교체해 버린다.
classList를 이용하는건
js에서 건드리는건 HTML element가 가지고있는 또하나의 요소 사용하는 것이다.
= element의 class내용물을 조작하는 것을 허용한다는 뜻
toggle
 토큰이 존재하면 토큰제거
토큰존재 하지않으면 토큰 추가
toggle function은 class name이 존재하는 지 확인한다.
class name이 존재하면 toggle은 class name을 제거하고, class name이 존재하지 않으면 toggle은 class name을 추가한다.
h1 {
  color: aqua;
}
.clicked {
  color: tomato;
}
const h1 = document.querySelector("div.hello:first-child h1");

function handTitleClick() {
  h1.classList.toggle("clicked");
}
h1.addEventListener("click", handTitleClick);
