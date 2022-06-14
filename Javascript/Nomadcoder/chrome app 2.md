****2.1 Basic Data Types****

데이터 타입의 종류

1. Number

1) 정수(Integer) // 1, 2, 3, 4 ...

2) 소수(Float) // 1.555, 2.545345 ...

- Number타입은 서로 연산기호를 이용하여 계산할 수 있다.

2. String

: 처음부터 끝까지 문자(Text)로 구성되어 있다는 의미

"Hello," + " My name is Nico" // Hello, My name is Nico

- String타입은 ""을 이용하여 입력하고 String타입의 합은 두개를 합

쳐서 출력한다.

****2.2 Variables****

variable는 값을 저장하거나 유지하는 역할 

const a(상수)0

Js에선 변수의 이름을 지정해줄때 띄어쓰기를 하지않는다 보통 대문자를 써서 표시해준다

길이가 긴 변수를 선언할 때 → Camelcase

ex. VeryLongVariableName

cf. Python에서는 very_long_variable_name

****2.3 const and let****

const는 constant(상수)를 줄인 것이고, 값이 바뀔 수 없다는 것을 나타낸다.

let은 variable값을 업데이트하고 싶을 떄 쓴다.

****2.4 Booleans****

data type 에는 숫자 , 문자 말고도

boolean 값으로 true,false가 있다.

undefined = 박스만 만들어 놓은 상태

null = 박스만들고 아무것도 안넣고 포장함

1. null: 컴퓨터에 값이 없음을 의도적으로 알리기 위해 채워진 값이다

2. undefined: let something; 처럼 변수에 값을 지정하지 않으면

메모리 상에 자리는 존재하지만 값이 채워지지 않은 채로 있다.

****2.5 Arrays****

Array[]

데이터를 나열하기 위한 방법 중 하나.

항상 [ ] 안에 콤마(,)로 데이터들을 나열한다. 변수도 쓰일 수 있고, boolean, text, 숫자 등 데이터 정렬이 가능하다.

```css
daysOfWeek=[a,b,c,d,e,f]
console.log(daysOfWeek[4]
daysOfWeek.push("g");
```

만약, 위의 변수에서 5번째 element 값을 알려주세요. 라고 한다면 어떻게 출력해야 할까?

ex) console.log(daysOfWeek[4]) 라고 해야 5번째 값을 출력할 수 있다.

daysOfWeek이란 변수에 하나의 값을 더 넣고 싶다면 다음과 같이한다.

ex) daysOfWeek.push(“holiday”) .push는 추가하는 기능.

****2.6 Objects****

object는 property를 가진 데이터를 저장해주며, { } 를 사용한다.

```jsx
const player = {
name : tomato,

color : red,

food : true,

};
```

console.log(player);

property를 불러오는 방법은 2가지가 있다.

```jsx
console.log(player.name); => tomato

console.log(player["name"]); => tomato
```

또한 property를 바꾸는 것은 가능하지만 선언된 object를 바꾸는 것은 불가능하다.

```jsx
player.color = "blue";

console.log(player.color); //blue
```

그리고 property를 추가 할 수도 있다.

설명이 필요하지 않은 데이터 리스트들은 array로,

설명이 필요한 정보가 담긴 데이터 리스트들은 object로!

****2.7 Functions part One****

function은 내가 계속 반복해서 사용할 수 있는 코드 조각이다. 

```jsx

function 함수명() {

실행코드

}

 함수명()
```

argument(인수)를 보내야 하는데 인수란 함수를 실행하는 동안 어떤 정보를 함수에게 보낼 수 있는 방법이다.

****2.8 Functions part Two****

**인수**란 함수를 호출할 때 사용되는 값 이다.

객체 안에 함수를 정의 할 때는 functionName : function(){}의 형태

```jsx
const player = {
name: "nico",

sayHello: function(otherPersonsName) {

console.log("Hello " + otherPersonsName + " nice to meet you!");

}

};
```

호출 하면 

```jsx
player.sayHello("lynn");// Hello lynn nice to meet you!
```

****2.11 Returns****

어떤 작업을 처리하고 그 결과를 return하기 위해 funtion을 사용한다.

function의 결과를 알고 싶을 떄 return을 사용한다.

데이터를 받아서 사용하거나 화면에 보여주기 위해 return을 사용한다.

console.log에서는 값을 가져올 수 없었다. 보여주기만 할뿐이다.

console.log는 콘솔에만 결과를 보여줄 수 있다. 브라우저에는 보여줄 수 없다.

****2.12 Recap****

return을 하면 function은 작동을 멈추고 결과값을 return하고 끝나버린다.

****2.13 Conditionals****

prompt는 사용자에게 창을 띄운다.

value의 type을 보려면 typeof를 사용한다.

```jsx
const age = prompt("How old are you?");

console.log(typeof age, parseInt(age));

const age= parseInt(prompt (“How old are you?”));
```

string은 대소 비교를 할 수 없다.

****2.14 Conditionals part Two****

isNaN 은 무언가가 NaN인지 판별하는 방법

condition은 boolean으로 판별가능해야 한다, (true , false)

```jsx
const age = NaN;

if (isNaN) {
  console.log("write a number");
}
```

****2.15 Conditionals part Three****

true || true // true

true || false // true

true && false // false
