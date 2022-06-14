****4.0 Input Values****

모든 것은 HTML에서 시작되어야 함. HTML에서 작성하고 자바스크립트로 기능을 구현.

먼저, HTML 코드 작성하기

1. 사용자가 이름을 작성할 수 있도록 input 태그를 작성한다.

안에 텍스트를 넣을 거니까, type="text"해주고, 안에 미리 작성할 말은 placeholder 안에 써주기

2. 그리고 옆에 버튼을 만든다.

Log In

3. div태그로 위의 것들 묶어주고, id="login-form"을 해준다.

왜 div태그로 묶는지 확실히는 모르겠지만, 내 생각에는 둘을 묶은 다음, 저 id를 통해서

자바스크립트에서 내가 원하는 태그들을 쉽게 찾기 위해서 묶어주는 것 같음.

input 안에 뭔가를 작성하고 로그인 버튼을 누르면 저장해야 되니까

자바스크립트로 그 기능 구현하기

그냥 html 태그를 가져올 수 없으니까 변수 안에 넣고 거기서 텍스트 받기

1. const loginInput = document.querySelector("#login-form input");

const loginButton = document.querySelector("#login-form button");

document 안에서 찾기. id="login-form"인 곳에서 input요소를 loginInput 안에 넣어주기

2. 버튼을 클릭하면, 내가 작성한 값을 콘솔에 보여주는 기능

loginButton.addEventListener("click, onLoginBtnClick);

3. 함수 만들기

function onLoginBtnClick(){

console.log(loginInput.value);

}

input의 내용을 가져오려면 value라는 property를 찾아봐야 됨.

****4.1 Form Submission****

input의 유효성 검사를 확인하기 위해서 input이 form안에 있어야 한다.

이름을 제출할 떄 웹페이지를 재시작 하고 싶지 않다.

****4.2 Events****

function이 하나의 argument를 받고 이것을 JS에 넘겨준다.

preventDefault()

어떤 event의 기본 행동이든지 발생되지 않도록 막는다.

function onLoginSubmit(event){

event.preventDefault(); // 브라우저가 기본 동작을 실행하지 못하게 막기

console.log(event);

}

loginForm.addEventListener("submit", onLoginSubmit); // submit 이벤트가 발생한다면, onLoginSubmit함수를 실행시킨다는 의미 // JS는 onLoginSubmit함수 호출시 인자를 담아서 호출함. 해당 인자는 event object를 담은 정보들

**★ 중요 ★**

form을 submit하면 브라우저는 기본적으로 페이지를 새로고침 하도록 되어있다.(form의 기본동작) << 우리가 원하는 것이 아님!

preventDefault() 함수를 추가함으로써 브라우저의 기본 동작을 막을 수 있다!!

이 preventDefault 함수는 EventListener 함수의 '첫 번째 argument' 안에 있는 함수이다. 첫 arument는 지금 막 벌어진 event들에 대한 정보를 갖고 있다.

JS는(기본적으로)argument를 담아서 함수를 호출하는데, 이 argument가 기본 정보들을 제공하고 있다. ex) 누가 submit주체인지, 몇 시에 submit을 했는지 등등 콘솔에 출력해보면 알 수 있음

(event) 및(tomato)를 적어주는 것은

form에서 발생한 submit event 관련 정보를 담을 용도로 onLoginSubmit 함수에 event라는 매개변수를 추가해줍니다.

****4.3 Events part Two****

JS는 함수를 실행시키는 동시에 그 함수에 첫번쨰 인자로 object를 넣어준다.

브라우저는 함수를 실행시켜주는 것만이 아니라 event에 대한 정보도 담아준다.

addEventListener 안에 있는 함수는 직접 실행하지 않는다

브라우저가 실행시켜주고 브라우저에서 해당 이벤트에 대한 정보 즉, object를 가지게 된다.

addEventListener의 함수에서 object에 대한 자리만 할당해주면 해당 이벤트가 발생시킨 정보들에 대한 object들을 볼 수 있다!

이때 해당 이벤트가 가진 기본 Default값을 발생시키지 않기 하게 위해선 preventDefault를 이용하여 막을 수 있다!
****4.5 Saving Username****

localStorage 브라우저에 무언가를 저장한 후 나중에 가져 올 수 있음.

localStorage.setItem("username", "nico");

localStorage.getItem("username")

localStorage.removeItem("username")

****4.6 Loading Username****

유저정보유무를 확인한다.

****4.7 Super Recap****

local storage가 정보를 저장하고 불러오고 삭제하는 브라우저가 가지고 있는 작은 DB같은 API

Key와 Value가 있다.
