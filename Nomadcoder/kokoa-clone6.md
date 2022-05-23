****6.0 Introduction****

.DS_Store는 맥 os나 윈도우에서 만든 보이지 않는 임시파일이다.

.gitignore는 무시하고 싶은 파일 이름을 기록하는 파일이다.

****6.1 Sign Up Screen part One****

index.html이라고 이름 짓는 이유 대부분의 웹서버가 디폴트로 index.html로 찾아보도록 설정되어있다.

div class = “name”은 div.name으로 

div id=”id”는 div#id하시면 자동완성 됩니다.

****6.2 BEM****

 ****BEM****

프로그래머들은 class를 사용하자고 결정했다.

**block**

**block_element**

**block_element—modifier**

내가 내 코드를 다시 볼 떄, 남들이 내 코드를 찾아볼 떄 이해에 도움을 줌

어떤 목적인가에 따라 이름을 짓는다.

**block**

재사용 가능한 기능적으로 독립적인 페이지 컴포넌트 

똑 떼어다가 어딘가에 쓸 수 있다.

**element(_ _)**

엘리먼트는 블럭을 구성하는 단위이다.

**Modifier(- -)**

블럭이나 엘리먼트의 속성을 담당한다.

생긴 게 조금 다르거나 다르게 동작하는 블럭이나 엘리먼트를 만들 떄 사용한다.

**불리언 타입**

**키-밸류(key-value)**

****6.3 Font Awesome****

font awesome에 자신이 원하는 아이콘을 복사할 수 있다.

스크립트는 항상 마지막에 있어야 한다.(body바로 위에)

아이콘 추가 방법

직접 이미지 아이콘 추가

SVG

1.fontawesome

2.kit 복사

3.아이콘 html 복사

****6.4 Sign Up Screen part Two****

**헤더작성**

어떤 페이지든 공통적으로 헤더를 가지고 있으므로 구분가능한 클래스 작성

form 작성

id pw 입력창과 버튼두개

form에서 버튼은 type submit으로 

****6.5 Status Bar CSS****

link:Css + enter: css링크 단축키

**web font** 

link보다 import를 추천한다.

body에 font-family 추가

**google font 넣는법**

1.import를 style 맨 위에 넣는다.

2.font-family를 body 안에 넣는다.

**css hack(justify-content대신 사용가능)**

-레시피 어디든 사용가능

-1.상위 박스: justify-content:center-중앙로 몰림

2.내부박스: width:33% 

3.중앙에 위치할 박스 

display:flex; justify-content:center;

4.오른쪽에 정렬할 박스: 

**font awesome 아이콘 크기 조절**

<i class="fa-solid fa-battery-full fa-xl"></i>

****6.6 Sign Up Screen part Three****

**리셋 css**

대부분의 태그에 margin:0, padding:0, border:0 등을 가진 css파일을 말한다.

파일

[https://cssdeck.com/blog/scripts/eric-meyer-reset-css/](https://cssdeck.com/blog/scripts/eric-meyer-reset-css/)

css파일에 넣어서 적용한다.

@import “reset.css”

**css 파일 나누기**

css파일을 여러파일을 따로 나누어서 다시 합칠 수 있다.

status-bar.css

@import “status-bar.css
