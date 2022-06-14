**3.17 States**

**state**

개발자 도구에서 가장 중요한 selector는 'state'다

조건을 나열해 여러 상황을 설정할 수 있음.

예 high-tag:hover low-tag:focus{

}

****3.18 Recap****

**:: placeholder**

:placeholder의 특성만 바꾸고 싶을 떄 사용

**::selection**

클릭해서 긁을 떄 발생

**::first-letter**

첫글자에만 적용된다.

**focus-whitin** 

자식이 focus되면 부모가 작동한다.

focus되는 children이 있으면 작동. 

div:focus-within{background-color:cyan}이면, div의 children이 focus 될 떄 {}가 작동

*form: hover input:focus{}의 경우엔 두 조건 모두 만족해야 {]안이 실행된다.

****3.19 Colors and Variables****

**color system**

1)hexadecimal color

2)RGB 방식

- **Variable**
    
    :root 라는 엘리먼트에 변수를 추가하는  것
    
    :root은 모든 document의 뿌리
