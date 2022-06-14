****6.1 Background****

random

```jsx
Math.floor(Math.random() * quotes.length
```

JS에서 이미지를 만들어서 html에게 추가하기

createElement 를 사용하자.

const images = ["0.JPG","1.JPG","2.JPG"]

const chosenImages = images[Math.floor(Math.random() * images.length)];

console.log(chosenImages);

const image = document.createElement("img");

image.src = `img/${chosenImages}`;

console.log(image);

- *appendChild() => body에 추가하는 역할

****6.2 Recap****

1. Math 객체 기능

Math.random() 0부터 1사이 무작위의 값을 반환해줌

Math.floor() 내림

Math.ceil() 올림

Math.round() 반올림

2. JS에서 html 요소를 생성

createElement(" ")

예를 들어,

document.createElement("img")일 경우 html 내에 img 태그를 생성
