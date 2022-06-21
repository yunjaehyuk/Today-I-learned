## React Part 2.1 **새로운 프로젝트 생성 & Bootstrap 사용하기**

**React-Bootstrap 라이브러리 설치**

레이아웃을 복사붙여넣기식으로 편하게 개발가능한 Bootstrap 라이브러리

**설치 1. 에디터에서 터미널켜고**

**설치 2. 어떤 스타일은 Bootstrap CSS 파일을 요구하는 경우가 있습니다.**

**ctrl + c**(미리보기 종료)

**react-bootstrap 사이트에서 UI 복사붙여넣기 하는법** 

 1 .  import {Button} from 'react-bootstrap’

1.  <Button variant="primary">Primary</Button>

대문자는 import해야 한다.

점 찍인 문자는 import하지 않아도 된다.      

<br/><br/>

## React Part 2.2 **이미지 넣는 법 & public 폴더 이용하기**

**대문만들기 & css파일에서 이미지넣기**

```css
.main-bg {
  height: 300px;
  background-image: url('Logo.png');
  background-size: cover;
  background-position: center;
}
```

html에서 src폴더의 이미지 넣을 떈

### **상품목록 레이아웃 만들기**

**상품이미지와 설명넣기**

외부에 호스팅해둔 이미지라면 이미지 절대주소만 넣으면 된다.

```jsx
<img src="https://codingapple1.github.io/shop/shoes2.jpg" width="80%"/>
```

html에서 src폴더 이미지 사용할 떈 import부터 해와야 된다.

화면을 가로로 3등분 하고 싶으면 

Bootstrap을 쓰면 레이아웃 짜는게 간편해진다.

```jsx
<div className="container">
  <div className="row">
    <div className="col-md-4">안녕</div>
    <div className="col-md-4">안녕</div>
    <div className="col-md-4">안녕</div>
  </div>
</div>
```

### **public 폴더의 용도**

이미지같은 static 파일의 경우 public 폴더에 보관해도 됩니다.

src 폴더에 있던 코드와 파일은 다 압축이 되는데 public 폴더에 있는 것들은 그대로 보존해줍니다.

그래서 형태를 보존하고 싶은 파일은 public 폴더에 넣으면 된다.

### public 폴더에 있는 이미지 사용할 떈

하지만 html에서 public폴더 이미지 사용할 땐 그냥/이미지 경로만 입력해도 된다.

권장되는 방식은 다음과 같다.

```jsx
<img src={process.env.PUBLIC_URL + '/logo192.png'} />
```
<br/><br/>
## React Part 2.3 **코드 길어지면 import export 하면 됩니다.**

export 하려면 

```jsx
let a = 10;
let b = 100;
export default 변수
export{변수1,변수2}
```

import 하려면 

```jsx
import 작명 from ‘파일경로’
import 작명 from './data.js';
```

복잡한 자료에서 데이터 뽑을 떈 시작기호만 잘보면 된다.

숙제1. 상품목록 컴포넌트화 하기

숙제2. 상품명 데이터바인딩도 해오기

숙제3. 반복적인 부분은 map반복문 써보기
    

<br/><br/>
## React Part 2.4 **리액트 라우터 1 : 셋팅이랑 기본 라우팅**

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
