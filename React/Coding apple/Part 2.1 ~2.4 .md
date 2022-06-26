## React Part 2.1 **새로운 프로젝트 생성 & Bootstrap 사용하기**

**React-Bootstrap 라이브러리 설치**

레이아웃을 복사붙여넣기식으로 편하게 개발가능한 Bootstrap 라이브러리

**설치 1. 에디터에서 터미널켜고**

**설치 2. 어떤 스타일은 Bootstrap CSS 파일을 요구하는 경우가 있습니다.**

**ctrl + c**(미리보기 종료)

**react-bootstrap 사이트에서 UI 복사붙여넣기 하는법** 

1.  import {Button} from 'react-bootstrap’

2.  <Button variant="primary">Primary</Button>

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

**html에서 src폴더의 이미지 넣을 떈**

html 안에서 이미지를 집어넣고 싶으면

이미지를 import 해오고 사용해야합니다.

### **상품목록 레이아웃 만들기**

**화면을 가로로 3등분 하고 싶으면** 

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

**상품이미지와 설명넣기**

외부에 호스팅해둔 이미지라면 이미지 절대주소만 넣으면 된다.

```jsx
<img src="https://codingapple1.github.io/shop/shoes2.jpg" width="80%"/>
```

html에서 src폴더 이미지 사용할 떈 import부터 해와야 된다.

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

**export default / import 문법**

상품정보들을 state로 만들고 싶은데 useState() 안에 넣기엔 너무 깁니다.

그럴 땐 다른파일에 보관했다가 import해올 수도 있습니다.

예를 들어서 data.js라는 파일이 있는데 거기 있던 변수를 App.js 에서 가져와서 쓰고 싶으면

```jsx
let a = 10;
let b = 100;
export default 변수
export {변수1,변수2} // 여러 변수를 내보내고 싶으면 이렇게 쓴다.
```

export default 변수명; 이렇게 쓰면 원하는 변수를 밖에서 내보낼 수 있다.

export 했던 변수를 다른 파일에서 사용하고 싶으면

**import 작명 from './파일경로'** 하면 됩니다.

```jsx
import 작명 from ‘파일경로’
import 작명 from './data.js';
```

복잡한 자료에서 데이터 뽑을 떈 시작기호만 잘보면 된다.

숙제1. 상품목록 컴포넌트화 하기

숙제2. 상품명 데이터바인딩도 해오기

숙제3. 반복적인 부분은 map반복문 써보기

<br/><br/>
## React Part 2.4 **저번시간 숙제 해설 (Card 컴포넌트 만들기)**

**숙제1. html 긴 부분 컴포넌트로 만들어보기**

따로 function을 만들어서 컴포넌트 하기

**숙제2. shoes를 Card 컴포넌트에 데이터바인딩 하기**

data.js 에 있던 데이터 정보를 card 컴포넌트에 props 전송하기

컴포넌트를 매번 다르게 보여주고 싶다면 

```jsx
<Card shoes={shoes[0]} i={1} />
<Card shoes={shoes[1]} i={2} />
<Card shoes={shoes[2]} i={3} />
```

```jsx
function Card(props){
  return (
    <div className="col-md-4">
      <img src={'https://codingapple1.github.io/shop/shoes' + props.i + '.jpg'} width="80%" />
      <h4>{ props.shoes.title }</h4>
      <p>{ props.shoes.price }</p>
    </div>
  )
}
```


**숙제3. map 반복문**
```
{
shoes.map(a,i)(()=> {
<Card shoes = {shoes[i]} i = {i + 1} />
}
```







