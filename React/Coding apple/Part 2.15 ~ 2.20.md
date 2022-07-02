## React Part 2.15 **멋있게 컴포넌트 전환 애니메이션 주는 법 (transition)**

### 전환 애니메이션 주는 법

 전환애니메이션은 부착하면 애니메이션 나오는 className 하나 만들고 원할 떄 부착한다.

1. 애니메이션 동작 전 className 만들기
2. 애니메이션 동작 후 className 만들기
3. className에  transition 속성 추가
4. 원할 때 2번 className 부착

**1. 애니메이션 동작 전 2. 애니메이션 동작 후 className 만들기**

```jsx
.start {
  opacity : 0
}
.end {
  opacity : 1;
}
```

**3. transition 추가**

```jsx
.start {
  opacity : 0
}
.end {
  opacity : 1;
  transition : opacity 0.5s;
}
```

**4. 원할 때 end 부착**

**리액트의 automatic batching 기능**

“버튼을 누를 떄마다 end를 부여해주세요.”

state에 따라서 className이 어떻게 보일지 작성하고

- 원할 때 fade를 변경했습니다.

```jsx
function TabContent({탭}){

  let [fade, setFade] = useState('')

  useEffect(()=>{
    setTImeout(()=>{ setFade('end') }, 100)
  return ()=>{
    setFade('')
  }
  }, [탭])

  return (
    <div className={'start ' + fade}>
      { [<div>내용0</div>, <div>내용1</div>, <div>내용2</div>][탭] }
    </div>
  )
}
```

**오늘의 숙제**

Detail 페이지 로드시 투명도 0→ 1 애니메이션을 주고 싶으면?

## Part 2.16 **props 싫으면 Context API 써도 됩니다.**

**Single Page Application**

(html 페이지가 하나인 사이트)

단점:

컴포넌트간 state 공유 어려움

부모컴포넌트 → 자식컴포넌트 

props 전송가능

props 전송은 부모 → 자식만 가능

### props 싫으면

**1.Context API(리액트 기본문법)**

props 전송없이 state 공유가능

**2.Redux 등 외부라이브러리**

## Part 2.17 **장바구니 페이지 만들기 & Redux 1 : Redux Toolkit 설치**

**장바구니 페이지 만들기**

페이지 하나 필요하면 route에 간다.

```jsx
<Route path="/cart" element={ <Cart/> } />
```

**<table> 레이아웃 사용법**

tr 넣으면 행 하나 생김

th,td 넣으면 열 하나 생김

**Redux 쓰는 이유**

Redux 사용하면 컴포넌트들이 props 없이 state 공유가능

js 파일 하나에 state들을 보관할 수 있는데

그걸 모든 컴포넌트가 직접 꺼내쓸 수 있습니다.

**Redux 설치 & 셋팅**

셋팅1. store.js 파일생성 코드 복붙

```jsx
import { configureStore } from '@reduxjs/toolkit'

export default configureStore({
  reducer: { }
})
```

셋팅2. index.js 가서 <Provide store={store}> 쓰기

```jsx
<React.StrictMode>
    <Provider store={store}>
      <BrowserRouter>
        <App />
      </BrowserRouter>
    </Provider>
  </React.StrictMode>
```

## Part 2.18 **Redux 2 : store에 state 보관하고 쓰는 법**

**Redux store에 state 보관하는 법**

state 하나를  slice라고 부름

step 1. createSlice( ) 로 state 만들고

createSlice는 useState()와 비슷한 역할을 한다.

step 2. configureStore( ) 안에 등록하면 됩니다.

**Redux store에 있던 state 가져다쓰는 법**

```jsx
(Cart.js)

import { useSelector } from "react-redux"

function Cart(){
  let a = useSelector((state) => { return state } )
  let a = useSelector((state) => state.user )
console.log(a)

  return (생략)
}
```

state

→ store안에 있던  모든 state가 된다.

## Part 2.19 **Redux 3 : store의 state 변경하는 법**

### **Redux의 state 변경하는 법**

1**.state 수정해주는 함수 만들고**

```jsx
reducers : {
    changeName(state){  // 함수이름(기존 state)
      return 'john' + state // john kim

    }
  }
```

**2.수정한 함수를 export해야함.**

```jsx
})

export let { changeName } = user.actions
```

1. **만든 함수 import 해서 사용 근데 dispatch() 로 감싸서 써야함**

```jsx
import { useDispatch, useSelector } from "react-redux"
import { changeName } from "./../store.js"

 function Cart() {
  let state = useSelector((state) => state )
  let dispatch = useDispatch()

(생략) 

<button onClick={()=>{
  dispatch(changeName())
}}>버튼임</button>
```

**store안에 있는 state를 수정하고 싶으면**

- state 수정해주는 함수를 store.js에 만들어두고
- 컴포넌트는 그걸 부르기만 하는 식으로 state 수정하게 되어있습니다.

왜냐하면 컴포넌트 100개에서 직접 ‘ kim’ 이라는 state 변경하다가 갑자기 ‘kim’이 123이 되어버리는 버그가 발생하면 범인 찾으려고 컴포넌트 100개를 뒤져야 한다.

## Part 2.20 **Redux 4 : state가 object/array일 경우 변경하는 법**

**state가 array/object인 경우 변경**

array/object의 경우 직접수정해도 state 변경된다.

```jsx
changeName(state) {
  state.name = 'park'
}
```

**결론** 

state가 object/array면 return 없이 직접 수정가능하다.

문자하나만 필요해도 일부로 {} 안에 담기도 한다.

action

state 변경함수라고 부른다.
