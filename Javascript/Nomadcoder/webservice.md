****2.2 Our First React Element****

React.JS는 어플리케이션이 아주 interactvie하도록 만들어주는 library 이다.

React dom은 모든 React element들을 HTML body에 둘 수 있도록 해준다.

**ReactDOM.render()** - render의 의미는 react element를 가지고 HTML로 만들어 배치한다는 것. 즉, 사용자에게 보여준다는 의미

**ReactDOM.render**(span, span이 가야할 위치)

- > 그래서 보통 body에 id=“root” 만들어서 span을 root 안에 두라고 함

**React.createElement**("span", {span의 property}, “span의 내용”)

- > property는 class name, id도 가능 style도 가능
- > 참고만 하고 외우지 말기. 이렇게 쓸 일 없음

바닐라JS는 HTML -> JS 순서

리액트는 JS -> HTML 순서

JS가 element를 생성하고 React JS가 그것을 HTML로 번역하는 것

React JS는 업데이트 해야 하는 HTML을 업데이트 할 수 있음

React JS에서는 모든 것이 Javascript로 시작한다.

유저에게 보여질 내용을 컨트롤 할 수 있다.

****2.3 Events in React****

두 가지 const를 render 하고 싶은 경우 div를 만든다

그리고 React.createElement("div", null, [span, btn]); 와 같이 배열을 만들어서 const를 넣어준다.

property에 eventListener 넣는 것도 가능.

클릭 - {onClick: () => console.log("I'm clicked")}

마우스엔터 - {onMouseEnter: () => console.log("mouse enter")}
