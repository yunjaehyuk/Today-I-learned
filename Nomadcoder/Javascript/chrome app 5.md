****5.0 Intervals****

interval = 매번 일어나야 하는 무언가!

setInterval(실행할 함수, 실행할 함수의 주기)!

****5.1 Timeouts and Dates****

```jsx
function getClock() {
  const date = new Date();
  clock.innerText = `${date.getHours()}:${date.getMinutes()}:${date.getSeconds()}`;
}
getClock();                                 //웹사이트 로드되자마자 시작
setInterval(getClock, 1000);                //웹사이트 로드 후 1초마다 시계가 돌아간다.
```

new Date() = “현재 시각”

date.getHours =”시간만 얻다”

date.getMinutes =”분만 얻다”

****5.2 PadStart****

```jsx
const hours = String(date.getHours()).padStart(2, "0");
  const minutes = String(date.getMinutes()).padStart(2, "0");
  const seconds = String(date.getSeconds()).padStart(2, "0");
  clock.innerText = `${hours}:${minutes}:${seconds}`;
```

"1".padStart(2, "0") => 길이가 1인 문자열있다, string의 시작 부분에 길이가 2가 되지 않는다면 앞 부분에 "0"이라는 문자열을 추가

padEnd는문자열을 맨 뒤에 더해준다.

number을 text로 변환 ex) String(new Date(). getHours())

**`padStart()`**
 메서드는 현재 문자열의 시작을 다른 문자열로 채워, 주어진 길이를 만족하는 새로운 문자열을 반환한다. 채워넣기는 대상 문자열의 시작(좌측)부터 적용됩니다.
