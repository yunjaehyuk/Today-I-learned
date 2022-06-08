# Github markdown 문법1



## 1. markdown에 관하여
### 1.1 markdown이란?

Markdown은 텍스트 기반의 마크업언어로 2004년 존그루버에 의해 만들어졌으며 쉽게 쓰고 읽을 수 있으며 HTML로 변환이 가능하다. 특수기호와 문자를 이용한 매우 간단한 구조의 문법을 사용하여 웹에서도 보다 빠르게 컨텐츠를 작성하고 보다 직관적으로 인식할 수 있다. 마크다운이 최근 각광받기 시작한 이유는 깃헙(https://github.com) 덕분이다. 깃헙의 저장소Repository에 관한 정보를 기록하는 README.md는 깃헙을 사용하는 사람이라면 누구나 가장 먼저 접하게 되는 마크다운 문서였다. 마크다운을 통해서 설치방법, 소스코드 설명, 이슈 등을 간단하게 기록하고 가독성을 높일 수 있다는 강점이 부각되면서 점점 여러 곳으로 퍼져가게 된다.

### 1.2 마크다운의 장점

### 1.21 장점 
<pre><code>1. 간결하다 2. 별도의 도구없이 작성가능하다.
3. 다양한 형태로 변환이 가능하다.
4. 텍스트(Text)로 저장되기 때문에 용량이 적어 보관이 용이하다.
5. 텍스트파일이기 때문에 버전관리시스템을 이용하여 변경이력을 관리할 수 있다.
6. 지원하는 프로그램과 플랫폼이 다양하다.</code></pre>

### 1.22 단점 
<pre><code>
1. 표준이 없다.
2. 표준이 없기 때문에 도구에 따라서 변환방식이나 생성물이 다르다.
3. 모든 HTML 마크업을 대신하지 못한다.
</code></pre>


<hr/>

## 2. 마크다운 사용법(문법)
### 2.1. 헤더Headers
<pre><code>
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
</code></pre>
# This is a H1
## This is a H2
### This is a H3
#### This is a H4
##### This is a H5
###### This is a H6
## 2.2 BlockQuote
이메일에서 사용하는 > 블럭인용문자를 이용한다.
<pre><code>
> This is a first blockqute.
>	> This is a second blockqute.
>	>	> This is a third blockqute.
</code></pre>


## 2.3 목록
### 순서 있는 목록(번호)
순서있는 목록은 숫자와 점을 사용한다.
1.첫번쨰
2.두번쨰
3.세번째
## 순서없는 목록(글머리 기호: *, +, - 지원)
<pre><code>* 빨강
  * 녹색
    * 파랑

+ 빨강
  + 녹색
    + 파랑

- 빨강
  - 녹색
    - 파랑
</code></pre>
* 빨강
  * 녹색
    * 파랑

+ 빨강
  + 녹색
    + 파랑

- 빨강
  - 녹색
    - 파랑
혼합해서 사용하는 것도 가능하다.

<pre><code>
* 1단계
  - 2단계
    + 3단계
      + 4단계
</code></pre>
* 1단계
  - 2단계
    + 3단계
      + 4단계


## 2.4 코드

4개의 공백 또는 하나의 탭으로 들여쓰기를 만나면 변환되기 시작하여 들여쓰지 않은 행을 만날때까지 변환이 계속된다.

## 2.41 코드블럭

* <pre><code>{code}</code></pre>

   
## 2.5 수평선 <hr/>

<pre><code>
* * *

***

*****

- - -

---------------------------------------
</code></pre>
* * *

***

*****

- - -

---------------------------------------
   
## 2.6 링크
* 참조링크

<pre><code>
[link keyword][id]
[id]: URL "Optional Title here"
//내부 링크

Link: [Google][googlelink]

[googlelink]: https://google.com "Go google"
//외부 링크
</code></pre>
   

## 2.7 강조
<pre><code>
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
~~cancelline~~
</code></pre>
*single asterisks*
_single underscores_
**double asterisks**
__double underscores__
~~cancelline~~
   
## 2.8 이미지 

img src="/path/to/img.jpg" width="450px" height="300px" title="px(픽셀) 크기 설정" alt="RubberDuck"></img><br/>
img src="/path/to/img.jpg" width="40%" height="30%" title="px(픽셀) 크기 설정" alt="RubberDuck"></img>
   
## 2.9 줄바꿈
3칸 이상 띄워쓰기( )를 하면 줄이 바뀐다.
   







## 출처   



**웹사이트**   
https://gist.github.com/ihoneymon/652be052a0727ad59601#%EA%B3%B5%ED%86%B5-%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4-markdown-%EC%9E%91%EC%84%B1%EB%B2%95




