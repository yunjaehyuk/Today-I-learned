## Part 2.1  **변수, 사칙연산 실력향상 과제**

```jsx
count += 1
    답 = document.querySelector('.answer').value
```

## Part 2.2 **setTimeout 타이머주는 법**

**X초 후 코드실행하려면** 

setTimeout(function() { 실행할 코드},  ms)

1초마다 코드 실행하려면

setInterval(function() {실행할 코드}, ms)

if var function 자바스크립트 문법

document,querySeletctor()       브라우저 사용법

setTimeout()

alert()

콜백함수 자리엔 만들어둔 함수를 넣을 수 있다.

**오늘의 숙제:**

위에서 만든 <div>안에 "5초 이내 구매시 사은품 증정" 이라는 문자가 있습니다.

1초마다 5라는 문자를 1씩 감소시켜봅시다.

0이 되면 <div>를 안보이게 처리합시다.

```html
<div class="alert alert-danger">
      <span id="num">5</span>초 이내 구매시 사은품 증정
    </div>
```

```jsx
<script>
    
      var count = 5;
    
      setInterval(function(){
        count -= 1;
        if (count >= 0){
          document.querySelector('#num').innerHTML = count;
        } 
      }, 1000);
     setTimeout(function(){
      $('.alert').hide();
     },6000)
    </script>
```

## Part 2.3 **정규식으로 이메일형식 검증해보기**

문자 검사하는 쉬운 방법

```jsx
'abc'.include('a')
```

정규식쓰면 문자검사 가능

```jsx
/a/.test('abcde')
```

regular expression (정규 표현식)
    
```
    $('form').on('submit',function(e){

  var 입력한값 = document.getElementById('email').value;
  if ( /\S+@\S+\.\S+/.test(입력한값) ){
    alert('이메일형식아님')
    e.preventDefault();
  }

});
    
```
    숙제 : 

폼 전송시 유저가 입력한 비번에 영어 대문자가 적어도 1개 있는지 검사해봅시다.

없으면 alert() 띄우거나 맘대로 합시다.
    
```
    $('form').on('submit',function(e){

  var 비번 = document.getElementById('pw').value;
  if ( /[A-Z]/.test(비번) == false ){
    alert('대문자없는데요')
  }

});
 
```
