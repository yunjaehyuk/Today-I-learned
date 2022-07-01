## Part 2.4 **코드 3줄로 캐러셀 (이미지 슬라이드) 만들기**

**캐러셀(carousel)**

회전목마

슬라이드되는 UI들

> **one-way 애니메이션들어간 UI 만드는 법은**
> 

1. 애니메이션 시작 전 화면 만들기

2. 애니메이션 종료 후 화면 만들기

3. 언제 종료화면으로 변할지 JS 코드짜기

4. transition 추가하기

**1. 애니메이션 시작 전 화면 만들기**

사진을 슬라이드 되서 보이게 하려면 사진을 가로로 길게 배치해야할 거다.

vw 단위는 브라우저 폭에 비례한 단위입니다. 100vw는 브라우저 폭의 100%입니다.

**2.버튼2 누른 후 최종화면 만들기**

## Part 2.5 **코드 3줄로 캐러셀 (이미지 슬라이드) 만들기2**

버튼3 기능 만들기

사진이 갑자기 4개가 되면?

## Part 2.6**함수의 return 문법 & 소수점 다루기**

function 문법

1. 긴코드 축약해서 쓸 수 있음
2. 파라미터 추가가능

함수쓰고 그 자리에 뭔가 뱉고 싶으면 return을 쓴다.

return은 함수 종료 기능도 갖고 있다.

**용도**

자료를 변환하려고 쓴다.

문자 → 문자 변환기

소수점 있는 숫자연산시 주의점

컴퓨터는 2진법으로 계산하기 떄문에 오차가 발생할 수 있다.

**소수점 반올림하는 법**

숫자.toFixed(몇자리)

문자로 변환된다.

```jsx
<script>
  console.log(vat(55555));

  function vat(a) {
    var num = (a * 1.1).toFixed(2);
    return parseInt(num)
  }
  </script> 
```

parseInt

```jsx
<script>
  console.log(price(70,false));

  function price(a,b) {
        if (b = false) {
            result = (a * 0.9).toFixed(2)
            return parseInt(result)
         }
        else{
          result = (a *0.9 - 1.5).toFixed(2)
          return parseInt(result)
        }
        }
  </script>
```

## Part 2.7 **스크롤 이벤트로 만드는 재밌는 기능들**

**문제 1. 스크롤바 100px 내리면 로고 폰트사이즈 작게 만들기**

**scroll 이벤트리스너**

```jsx
window.addEventListener('scroll', function(){
    
  })
```

유저가 얼마나 스크롤바 내렸나?

 window.scrollY

현재 위치부터 강제로 스크롤하기 

       window.scrollBy(x,y)

**문제 2. 회원약관 끝까지 읽으면 alert 띄우기**

문장에 스크롤바 만들기

```html
<div style="width: 200px; height: 100px; overflow-y:scroll">
```

overflow-y:  scroll

내용물이 넘치면 스크롤바로 만들어라
