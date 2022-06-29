## Part 2.23 **localStorage로 만드는 최근 본 상품 기능**

웹사이트를 새로고침하면 state 초기값으로 돌아감

→ 서버로 DB에 영구저장하면 된다..

### localStorage

1.브라우저에서 제공하는 데이터 저장소다.

2.key: value 형태로 저장가능

3.문자 데이터만 저장가능

4.사이트에 재접속해도 남아있다.

**데이터 저장**

localStorage.setItem(’이름’,’값’)

**데이터 출력**

localStorage.getItem(’이름’)

**데이터 삭제**

localStorage.removeItem(’이름’)

- 데이터를 수정하는 문법은 없다.
- array/object을 localStorage로 저장하려면 JSON으로 바꾸면 된다.
- JSON → array/object 변환은 JSON.parse() 이다.

**Session Storage**

사이트를 끄면 데이터가 날아간다.

## Part 2.24 **실시간 데이터가 중요하면 react-query**

**ajax 성공시/실패시 html 보여주려면?**

 **몇초마다 자동으로 ajax 요청?**

**실패시 몇초 후 요청재시도?**

**React query**

실시간 데이터를 계속 가져와야하는 사이트들이 쓰면 좋다.

**설치방법**

1. 터미널 npm install
2. import 함수
3. <QueryClientProvider client={queryClient}></>

**서버에서 유저이름 가져와 보여주기(react-query)**

장점1. 성공/실패/로딩중 쉽게 파악가능

### Part 2.25 **성능개선 1 : 개발자도구 & lazy import**

**React DevTools**

props 보냈는데 왜 출력 안되는 것?

왜 이미지 안나옴?

**Profiler 성능 측정** 

성능저하되는 컴포넌트 범인 찾기

**Single Page Application 특징**

발행하면 js 파일 하나에 모든 코드 다 쑤셔넣음

**lazy import**

지금까지 만든 App / Detail / Cart 모든 내용이 들어있어서 **파일사이즈가 좀 큽니다.**

js 파일을 **잘게 쪼개면** 됩니다.

```jsx
const Detail = lazy( () => import('./routes/Detail.js') )
const Cart = lazy( () => import('./routes/Cart.js') )
```

lazy 문법으로도 똑같이 import가 가능한데 이 경우엔

"Detail 컴포넌트가 필요해지면 import 해주세요" 라는 뜻이 됩니다.

그리고 이렇게 해놓으면 Detail 컴포넌트 내용을 다른 js 파일로 쪼개줍니다.

그래서 첫 페이지 로딩속도를 향상시킬 수 있습니다.

필요할 것 같으면 씁시다.

## Part 2.26 **성능개선 2 : 재렌더링 막는 memo, useMemo**

**재렌더링 막으려면 memo**

꼭 필요할 떄만 재렌더링하려면 memo를 쓴다.

memo로 재랜더링오래걸리는 컴포넌트를 감싸낳서 한 번만 실행하게된다.

**memo의 원리**

props가 변할 떄만 재랜더링해줌

## Part 2.27 P**WA 셋팅해서 앱으로 발행하기 (모바일앱인척하기)**

**PWA**

웹사이트를 모바일 앱처럼 설치해서 쓸 수 있음

1.설치 마케팅 비용적음

2.아날로그 유저들 배려

3.html css js 만으로 앱까지

4.푸시알림, 센서등

**service-worker.js** 

오프라인에서도 사이트열 수 있게 도와줌

**cashing**

미리 하드에 데이터를 저장해놓는 행위
