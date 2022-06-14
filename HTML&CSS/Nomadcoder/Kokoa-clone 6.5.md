****6.6 Sign Up Screen part Three****

width %값

퍼센트로 사이즈를 지정할 떄 100%를 주면 창크기에 상관없이 100%꽉차게 된다.

70%를 주면 70%내에서만 꽉차게 크기가 바뀐다.

****6.7 Log In Form part One****

****6.8 Log In Form part Two****

not

뭔가가 적용되는 걸 원하지 않을 떄  이것을 제외한 나머지에 적용하고 싶을 떄 사용

css에서 코드를 읽을 떄 위에서 아래로부터 코드를 읽는다. 코드의 순서가 매우 중요하다. 코드 순서가 다르면 css가 적용되지 않을 수 있다.

****6.9 Recap and Forms****

style.css 파일에는 font-family와 같이 모든 스크린에 적용될 수 있는 스타일을 써놓기

form에는 두가지 속성을 가지고 있다.

**action**

어떤 페이지로 data를 보낼건지 지정할 수 있다.

action에 적어 놓은 URL에 해당하는 파일이 존재해야한다.

입력 정보가 URL에 포함된다.

**method**

POST방식

백엔드 서버에 정보를 전송하는 방식

data를 서버로 보내는 방식

GET방식

보안에 취약해서 비번이나 아이디를 보낼 수 없다.

****6.10 Navigation Bar part One****

navigation 안의 ul 안에 많은 li들로 구성되는데, 검색엔진 구글도 navigation을 찾아서 ul안의 li안에 link를 가져오게끔 설정되어 있다.

nav>li>li*(필요한 갯수)>a

점 3개는 ellipsis 라고 부른다.

속성과 class이름이 똑같아도 상관없다.

메인 style.css에 다른 요소의 css를 import할 떄, 순서를 지키는 것이 중요하다.

****6.11 Navigation Bar part Two****

**box-sizing**

박스의 크기를 어떤 것으르 기준으로 계산할지를 정하는 속성

`box-sizing: content-box | border-box | initial | inherit`

content-box: 콘텐트 영역을 기준으로 크기를 정함

border-box: 테두리를 기준으로 크기를 정함

initial: 기본값을 설정

inherit:부모의 속성 값을 받음

**position:fixed**

**bottom: 0**

**이후 배열이 깨지는 이유**

width:100%가 부모의 너비를 다 받는다. 

• css 속성에서 `position:fixed`는 `absolute`와 마찬가지로 해당 element는 전체 css flow에서 벗어나게 된다.

****6.12 Border Box****

**css box padding의 원리**

200px 박스에 paddin-left:50px;를 주면, css는 기존 박스의 가로를 유지하기 위해 50만큼의 박스를 늘림

이를 막기 위해서 box-sizing:border-box를 쓰면 box의 크기를 유지한 채 padding을 줄 수 있다.

****6.13 Navigation Bar part Three****

position:absoulute; 는 정중앙. absolute는 해당 element의 가장 가까운 relative를 가진 부모 기준으로 움직인다. 기본적으로 body가 그에 해당하며 따로 원하는 기준이 있다면 그 cotainer에 position: relative를 준다.

display:flex는 부모 요소만 사용할 수 있다는데 왜 

**.nav_notification에서 사용할 수 있나요?**

**왜 top,btoom, left,right가 반대일까요?**

position 기본값이 좌 상단에서 시작하기 때문이다.

padding을 준다고 생각하면 된다.
