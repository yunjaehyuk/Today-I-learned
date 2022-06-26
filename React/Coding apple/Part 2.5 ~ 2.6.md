## React Part 2.5 **리액트 라우터 1 : 셋팅이랑 기본 라우팅**

**페이지 나누는 법(리액트 사용)**

/detail로 접속하면 상세페이지보여주고

/cart로 접속하면 장바구니페이지 보여준다.

index.html 하나밖에 사용안한다.

1.컴포넌트 만들어서 상세페이지 내용 채움

2.누가/detail 접속하면 그 컴포넌트를 보여준다.

**라우팅**

페이지 구분하는 거

react-router-dom 라이브러리 쓰면 쉽게 만들 수 있다.

**리액트 라우터 설치**

1. 터미널에 npm install react-router-dom@6를 입력한다.
2. index.js에 가서 아래의 코드를 입력한다.

```jsx
<BrowserRouter>
    <App />
    </BrowserRouter>
```

1. import {Routes, Route, Link} from 'react-router-dom’를 App.js에 가져온다.

내가만든 js파일들은 경로가 “ ./” 로 시작한다.

없는 것들은 라이브러리이다.

**라우터로 페이지 나누는 법**

```jsx
(App.js)

import { Routes, Route, Link } from 'react-router-dom'

function App(){
  return (
    (생략)
    <Routes>
      <Route path="/detail" element={ <div>상세페이지임</div> } />
      <Route path="/about" element={ <div>어바웃페이지임</div> } />
    </Routes>
  )
}
```

```jsx
<Route path="/" element={ 
  <>
   <div className="main-bg"></div>
   <div className="container">
     <div className="row">
       { shoes.map((a, i)=>{
         return <Card shoes={shoes[i]} i={i} ></Card>
        })}
      </div>
    </div> 
  </>
} />
```

1. 우선 상단에서 여러가지 컴포넌트를 import 해오고
2. <Routes> 만들고 그 안에 <Route>를 작성합니다.
3. <Route path="/url경로" element={ <보여줄html> } /> 이렇게 작성하면 됩니다.

**페이지 이동 버튼** 

```jsx
<Link to="/">홈</Link>
<Link to="/detail">상세페이지</Link>
```

Route

웹사이트의 페이지이다.

**숙제**

상세페이지 컴포넌트로 만들기

## React Part 2.6 **리액트 라우터 2 : navigate, nested routes, outlet**

폴더 어떻게 나눔

**Q. 폴더구조?**

-비슷한 파일끼리 폴더로 묶는게 끝

대문자 용어는 리액트에서 import해야 한다.

```jsx
import { Routes, Route, Link, useNavigate, Outlet } from 'react-router-dom'
```

### **1**.**페이지 이동기능을 만들고 싶으면**

**userNavigate() 함수**

/detail 페이지로 이동하는 버튼 만들기

```jsx
<Nav.Link onClick={()=>{ navigate('/')}}>Home</Nav.Link>
            <Nav.Link onClick={()=>{ navigate('/detail')}}>Detail</Nav.Link>
```

navigate(”이동할 페이지”)

**뒤로 가기 버튼** 

```jsx
<Nav.Link onClick={()=>{ navigate(-1)}}>Detail</Nav.Link>
```

-1 넣으면 뒤로 1번 가기

2 넣으면 앞으로 2번 가기

### **2.404페이지**

유저가 이상한 경로로 접속했을 떄 ‘없는 페이지입니다’ 를 보여주고 싶을 떄 사용한다.

```jsx
<Route path="*" element={ <div>없는페이지임</div> } />
```

### **3.서브경로 만들 수 있는 Nested Routes**

/about/member로 접속하면 회사멤버 소개하는 페이지

/about/location으로 접속하면 회사위치 소개하는 페이지

를 만들고 싶으면 어떻게 합니까.

```jsx
<Route path="/about" element={ <About/> } >  
  <Route path="member" element={ <div>멤버들</div> } />
  <Route path="location" element={ <div>회사위치</div> } />
</Route>
```

**Nested Route**

<Route>안에 <Route>를 넣을 수 있는데 이걸 Nested routes 라고 부릅니다.

태그안에 태그가 들어간 것을 말한다.

**장점2**

nested route 접속시엔 element 2개나 보임

**Q. <div>는 안보이는데요**

실은 위처럼 코드짜면 /about/member로 접속시 <About>안에 <div>맴버들</div>을 보여준다.

그래서 <About> 컴포넌트 안에 <div>를 어디다 보여줄지 표기해야한다.

```jsx
function About(){
  return (
    <div>
      <h4>about페이지임</h4>
      <Outlet></Outlet>
    </div>
  )
}
```

위에서 import해온 

**<Outlet>**

 nested routes안의 element들을 어디에 보여줄지 표기하는 곳입니다.

그래서 이렇게 해두면

/about/member로 접속시 <Outlet>자리에 아까의 <div> 박스들이 잘 보입니다.

그래서 유사한 서브페이지들이 많이 필요하다면 이렇게 만들 수 있다.

**Q.nested routes 언제 씀?**

여러 유사한 페이지가 필요할 떄

1. 이런식으로 UI 만들면 뒤로가기 버튼 이용가능
2. 페이지 이동이 쉬움

**오늘의 숙제 :**

▼ /event/one 페이지로 접속하면 하단처럼 생긴 페이지가 떠야합니다.

![https://codingapple.com/wp-content/uploads/2022/04/%EC%BA%A1%EC%B2%98445.png](https://codingapple.com/wp-content/uploads/2022/04/%EC%BA%A1%EC%B2%98445.png)

▼ /event/two 페이지로 접속하면 하단처럼 생긴 페이지가 떠야합니다.

![https://codingapple.com/wp-content/uploads/2022/04/%EC%BA%A1%EC%B2%9844554.png](https://codingapple.com/wp-content/uploads/2022/04/%EC%BA%A1%EC%B2%9844554.png)

위 2개의 페이지들을 nested routes 써서 아무렇게나 만들어봅시다.

```
<Routes>
  <Route path="/event" element={<EventPage/>}>
    <Route path="one" element={<p>첫 주문시 양배추즙 서비스</p>}></Route>
    <Route path="two" element={<p>생일기념 쿠폰받기</p>}></Route>
  </Route>
</Routes>
}
};
function EventPage(){
  return (
    <div>
      <h4>오늘의 이벤트</h4>
      <Outlet></Outlet>
    </div>
  )
}


```
