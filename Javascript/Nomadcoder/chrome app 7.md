### 7.0 Setup

1. html

1) Todo-list 를 만들기를 원하니 html 에 form 태그로 구조를 만들어 준다. 나중에 JavaScript에서 만지기 쉽게 id는 todo-form으로 설정

2) form 자체는 submit이라는 기본 기능을 내장하는 하나의 묶음 밖에 되지 않는다. 우리는 이용자가 todo-list 에 무언가 기입하는 것을 원하기 때문에 form 태그 안에 input 태그를 넣어 'text'를 타이핑할 수 있는 기능을 추가한다.

3) 그 밑에 ul 태그를 생성하여 todo-list에 작성 된 text가 저장 및 나열될 수 있게 한다.

2. JavaScript

1) 앞에 html에서 만든 구조 3가지 ('todo-form', 'todo-form 안의 input', 'todo-list') 에 접속하기 위해 항상 길게 타이핑하는 것은 비효율적이므로 단축을 위해 각각 변수로 설정한다.

2) 이전 greeting 강의에서 form 태그에서의 event는 submit를 발생시키고, 브라우저는 기본값으로 설정되어 있는 새로고침을 하게 된다. 우리는 todo-list를 작성한다고 새로고침 되는 것을 원치 않기 때문에(todo-list를 1,000번 작성한다고 가정한다면 불필요한 새로고침이 1,000번 발생하고 1,000번의 랜덤한 이미지가 로드될 것이다. -> 데이터적으로 비효율적, 시각적으로 불편)

event.preventDefault() 로 기본값을 없애준다.

3) text 상자 안에 글을 작성하고 enter를 눌렀을 때 그 글이 초기화 되게 만들기 위해 toDoInput.value = ""; 을 통해 value를 빈 텍스트로 한다.

4) text 상자를 비게 하는 것은 좋은데 그 전에 이용자가 입력한 텍스트를 저장해야 나중에 ul태그 안에 사용할 수 있기 때문에 toDoInput.value = ""; 로 기입한 텍스트가 사라지기 이전에

const newTodo = toDoInput.value; 를 정의하여 기입한 텍스트가 newTodo라는 값에 저장되게 한다.

5) 앞의 세 가지 동작(기본값방지, 텍스트 저장, text상자비우기)는 한번에 이루어지는 세트이기때문에 효율성 및 편의를 위해 함수로 묶어준다.

function handleTodoSubmit() {

event.preventDefault();

const newTodo = toDoInput.value;

toDoInput.value = "";

}

6) todo-form 안에서 submit이 발생하는 특정 상황에서 함수handleTodoSubmmit을 실행 시키기 위해

toDoform.addEventListner("submit", handleTodoSubmit); 을 기입한다.

(함수 handleTodoSubmit이 항상 실행되고 있는 상태라면 text 창은 항상 비어있는 상태 일 것이기 때문에

**결과** 

기존함수 handleToDoSubmit()가 텍스트 상자 안의 제출한 텍스트를 초기화한다.

**해야할 것**

웹사이트 화면에 ul안의 li태그와 그 안에 속하는 span 태그를 만들고 웹 화면에서 보이게 한다.

### 7.1 Adding ToDos

0. 이전 영상에서 우린 hadle.ToDoSubmit() 함수를 만들어

1) event.preventDefault(); // 새로고침을 막고

2) const newTodo = toDoInput.value; // submit하는 텍스트를 저장하고

3) toDoInput.value = ""; // 텍스트상자 안의 텍스트를 초기화시켰다.

이제 우린 방금 전 입력한 텍스트가 페이지에서 보여지는 것을 원하기 때문에 그에 맞는 코드를 작성할 것이다.

**1. html 돌아보기**

우린 이미 html에 todo-list라는 id를 가진 ul태그를 작성해 놓았고, 새로운 텍스트가 입력 될 때마다 그 안에 li 태그를 생성하여 나열하고 싶다. 이것을 JS에서 관여할 수 있도록 코드를 짜는 것이 필요하다.

**2. JavaScript - todo list를 웹페이지에서 시각화하기**

1) const li = document.createElement("li"); // li를 입력했을 때 html에서 li태그를 생성하게 명령한다.

2) const span = document.createElement("span"); // span이 정확히 왜 필요한지는 아직 잘 모르겠지만, 니꼬의 말에서 유추해보면 나중에 리스트 삭제 시 필요한가보다. 아무튼 span이라는 const가 html 내에서 span태그를 만들게끔 한다.

3) li.appendChild(span); // li 태그 안에 자식을 span 태그로 하게끔 한다. 아직 span을 굳이 왜 만드는지는 정확히 이해 x

4) span.innerText = newTodo; // span이라는 태그 안의 텍스트가 앞에서 설정한 new Todo라는 객체가 되도록 한다. newTodo는 텍스트에 입력한 value값

ex) 텍스트 상자 안에 "안녕하세요"라고 입력하면 newTodo는 "안녕하세요"이므로 span안의 텍스트는 "안녕하세요"가 될 것이다.

5) toDoList.appendChild(li); // html의 ul 태그 안에 li 를 속하게 한다. (span을 li에 속하게 한 것과 동일)

3. 함수 piantTodo(newTodo)를 함수 handleTodoSubmit()에 추가

우리가 텍스트를 기입하고 submit 할 때마다 원하던 기능들을 실행시키기 위해 위에서 만든 함수 paintTodo(newTodo)를 함수 handleTodoSubmit()에 추가한다.

기존 함수 handleToDoSubmit()가 텍스트 상자 안의 텍스트를 초기화하는 기능까지만 했다면, 

**결과**

**paintToDo(newTodo)추가 후에는** **제출한 텍스트를 매번 html의 ul안에서 li태그와 그 안에 속하는 span 태그를 만들고 span에 텍스트로 남겨 웹 화면에서 보일 수 있는 것 까지 되게 한다.**

**해야할 것**

하지만 우리가 만든 todo list 는 아직 삭제를 하지 못하고, 새로고침시 초기화 되어 화면의 todo list가 날라가 버린다. 다음 영상에서는 니꼬가 이 부분에 대해 알려줄 것 같다. 아무래도 이전에 배웠던 조건문 if를 이용한 tag 삭제 or 생성 그리고 생성된 span value를 localStorage에 저장 하는 방식으로 진행하지 않을까 싶다.

### ****7.2 Deleting To Dos****

**윈도우 이모지**

윈도우 + . 

1. JS에서 html 내부에 button 태그 만들기

1) const button = document.createElement("button"); // html에 button 태그를 생성할 수 있도록 button이라는 객체 정의

2) button.innerText = "❌"; // 사용자가 버튼을 누르면 텍스트가 삭제되는 기능이 있다는 것을 인식시키기 위해 버튼 내부 텍스트를 "❌"로 정의 (윈도우 기준: window 키 + . )

3) button.addEventListener("click", deleteToDo); // 버튼에서 이벤트가 발생했을 때 삭제 기능을 담당하는 함수가 실행되도록 한다. 여기에선 "click"이 발생 시, deleteToDo함수가 실생되도록 함

2. 삭제 기능을 담당하는 함수 생성

1) const li = event.target.parentElement; // 이벤트가 발생했들때.해당객체를지정하여.그것의부모태그를지정;

2) li.remove(); // 위에서 지정된 것을 삭제;

3. 정리하면

1) button.addEventListener("click", deleteToDo); 에서 클릭이 발생하면 deleteToDo함수가 실행된다.

2) 

```jsx
function deleteToDo(event) { 
const li = event.target.parentElement; li.remove(); 

}
```

해야할 것

website에 text저장하기

## ****7.3 Saving To Dos****

0. 이전 영상에서 우리는 추가와 삭제가 가능한 멋진 todo-list를 화면에 구현했다..!

하지만 새로고침을 하거나 이용자가 누구인가와 관계없이 똑같은 todo-list가 나온다면 우리는 todo-list를 그 때마다 계속해서 작성해야할 것이다. 만약 todo-list를 1,000개 작성했는데 단숨에 날라간다면...? 그건 어딘가 부족한 todo-list 일 거다. 그래서 우린 todo-list에 나타낸 텍스트를 저장하는 기능이 필요하다.

**1. todo - list의 배열 생성**

1) const toDos = [ ]; // toDo에 들어오는 텍스트를 배열로 묶어 보관하기 위해 빈 array를 생성해준다.

**2. 저장 기능을 함수를 정의한다.**

1) 아직 기능을 하진 않지만 우리는 화면에 나타낸 텍스트를 저장할 것이기 때문에 대충 그러한 기능을 하는 함수가 있다고 치고 빈 함수

function saveToDos( ) {

};

를 생성한다.

2) 앞에서 만들었던 함수 handleToDosubmut( ); 의 맨 마지막에 저장 기능을 실행할 saveToDos(); 넣어두고 다음에서 기능을 구현한다.

**3. todo - list를 저장하는 기능을 수행하는 함수 설정**

1) function saveToDos( ) { localStorage.setItem("todos",toDos); } 에 "todos"라는 이름의 카테고리로 저장한다.

2) 하지만 이렇게 저장하게 되면 직접 localStorage 에서 확인해봤을 때 값들이 array안에서

string의 형태가 아닌 상태로 저장된다.

예) key: todos value: a,b,c

3) 하지만 우리는 값들을 string의 형태로 toDos라는 array에 집어넣고 싶기 때문에 니꼬가 알려준 JSON.stringify() 라는 객체를 사용한다. 이 도구는 우리가 대입한 값을 알아서 string의 형태로 바꿔줄 것이다.

예) key: todos value: ["a", "b", "c"]

### ****7.4 Loading To Dos part One****

JSON.parse()는 string을 배열로 바꾸게해준다.

1. To-Do-List 작성시 localStorage 에 저장이 됩니다.

2. 근데 저장이 될때 string data type 으로 저장이 되요. (예: "[a,b,c,d,e]")

3. 그래서 JSON.parse()를 통해 string data type을 object로 바꾼거에요. 근데 이 Object는 Array 같이 바뀌었어요. 즉 index를 통해 value를 access할수 있어요

예: "[a,b,c,d]" (string) => [a, b, c, d] (array);

array[0] = a; array[1] = b; array[2] = c; array[3] = d

5. array 형태가 된 값을 parsedToDos 라는 const variable 에다가 넣어놨어요.

6. 이 상태에서 parsedToDos 는 array 형태라고 가정했을때 .foreach() 라는 function 을 사용할수 있는데 이건 mdn 웹사이트 가면 나오지만 그냥 단순히 array 에 들어있는 모든 값을 iterate (순찰(?)) 할수 있는 function 입니다.

7. 즉 index 0 부터 마지막 index 까지 한바뀌 도는건데 돌면서 그 값들을 item 라는 곳 또는 element에 (이름은 정하기 나름) 저장이 되는거에요.

```jsx
Array = [ a, b, c, d]

Array.foreach( (item) => console.log(item))

// output:

a

b

c

d
```

local storage에 array로 저장이 안되기 때문에 JSON.stringify로 array처럼 생긴 string으로 저장한 후 다시 JSON.parse 이용해 array로 꺼내는 방법이네요

array.foreach는 받아온 array를 for 반복문 없이 item 하나씩 function에 넣을 수 있다.

결과ㅏ 

로컬 스토리지에 문자가 저장되고ㅗ 

앞으로 행야할 것 

새로고침해도 이전의 toDos들이 array에 복원되는 것

### ****#7.5 Loading To Dos part Two****

**결과**

로컬 스토리지에 문자가 저장되고 이를 웹사이트에 출력할 수 있다. 새로고침해도 예전 toDos array를 가지고 와서 toDos array에 복원해주었다.

**앞으로 해야할 것**

로컬 스토리지를 지울떄마다 업데이트 하기

### ****#7.6 Deleting To Dos part One****

local storage는 toDos array를 복사해두는 곳이다.
