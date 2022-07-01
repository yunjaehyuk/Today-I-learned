## CSSOM이란?

즉, 임베디드된 스타일이나, CSS 파일에 정의한 CSS나, html 태그에 정의한 style 요소들을 비롯해서 이런 스타일이 따로 지정되어 있지 않아도 브라우저 상에서 기본적으로 가지고 있는 스타일에 대한 모든 정보들을 합쳐서 CSSDOM 이라는 트리

CSSOM에는 우리가 정의한 스타일 뿐 아니라 브라우저에서 기본적으로 설정된 모든 속성 값들이 cascading rule에 의해 정의되어 있는데 이것을 computed styles

CSSOM에는 계산된 모든 스타일에 관련된 속성들이 포함되어 있다

- 브라우저가 html 파일을 읽게 되면 제일 처음 DOM Tree를 만들고, 그 다음에 CSS파일을 읽은 다음 스타일을 모두 계산해서 최종적으로 확정된 CSSOM을 만들게 된다.
- 그 다음 DOM과 CSSOM을 합해서 사용자에게 최종적으로 브라우저에 표기될 것들만 render tree로 만들어진다 (DOM + CSSOM = Render Tree)

### 출처

**CSSOM**

[https://dkmqflx.github.io/frontend/2020/09/14/jscssom/](https://dkmqflx.github.io/frontend/2020/09/14/jscssom/)
