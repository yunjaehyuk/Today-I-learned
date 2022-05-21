### 2.1 Setup and Errors

 **브라우저와 HTML**에서 중요한 부분  

브라우저는 아무런 오류가 없다. HTML문법을 따르지 않아도 언제나 사용자에게 콘텐츠를 보여준다. 브라우저는 HTML 파일에 에러가 있다고 알려주지 않는다.

- 단점은 브라우저가 무엇이 잘못된거지 알려주지 않는다는 것.
- 장점은 우리가 실수를 하더라도 페이지에 접속한 유저는 콘텐츠를 볼 수 있다는 것.

### ****2.2 Our First HTML Tag****

HTML은 브라우저에게 이것이 어떤 태그인지 알려주는 역할을 한다.

1. **HTML tag** 사이에 넣는 텍스트가 무언가가 된다 (title, image, 등등)

2. 브라우저는 아무의미가 없어도 이해하려한다

3. h1 = header no.1, h2 = header no.2 . . . h6까지 존재

4. 태그는 닫아야한다.

5. 브라우저는 내가 만든 태그를 사용하지 못한다

### ****2.3 More Tags and Prettier****

 orderded list = 순서가 있는 리스트

 unordered list = 순서가 없는 리스트 (ul)

 리스트 안에 사용할 수 있는 태그 = list item (li)

### ****2.4 Tag Attributes****

### a

a = anchor를 뜻함 (link를 떠올리면 됨) (추가적인 정보가 필요함)

### attributes

 태그에 추가하는 정보

**href** = http reference라고 함 (anchor 태그에만 추가 가능)

**target** = 기본값은 self이고, _blank 입력 시 새 탭에서 링크가 열림

**img** = 다른 태그와 다르게 /로 닫는 태그가 없다 (자체 닫기 태그이기 때문)

**src** = img 안에 사진을 집어넣음 (img에서 작동)

### ****2.5 More Tags and Head****

**같은 폴더에 이미지가 있을 경우** 이미지 이름.확장자

다른 폴더일 경우 폴더/이미지.확장자 (경로 표기 법)

모든 HTML 문서는 로 시작

HTML 문서는 HEAD(웹사이트의 환경 설정, 외부적으로 보여지지 않는 설정), BODY(사용자가 볼 수 있는 내용)로 구성됨

title = 제목 설정

브라우저 화면상에 보여질 내용들은 body에 있어야 함.

**1. 상대경로**

기준 : 현재 웹페이지의 소속 폴더가 기준점

**.** : 현재 웹페이지가 소속된 폴더

**..** : 현재 웹페이지의 부모 폴더

자식폴더명 : 현재 소속된 폴더의 자식 폴더

현재 위치를 '나'로 기준을 삼고 상대를 찾는 표현

**2. 절대경로**

기준 : 누구나 다 알고있는 동일한 위치를 기준으로 상대를 찾는 표현

'/' 기준 -> '/' 는 웹사이트의 루트 폴더 > "http://localhost:8090"

'/WebClientTest' == 'WebContent'

### ****2.6 Its All About the Head****

**meta tag** = 부가적인 요소 라는 뜻 (content, name attribute를 가짐), 구글에서 검색할 떄 보여줌(description)

**charset** = 한글 등 문자 표시하게 해줌

**language** = 사이트에 사용되는 언어 표기 (검색엔진에게 알려줌)

### ****2.7 More Tags****

**mdn** 

html element 요소 찾는 것이 가능하다.

**title** 

글자에 마우스를 올리면 나타남. 태그의 속성이다.

**반복되는 단어 한방에 수정**

Ctrl + D(한번씩 일일이 눌러줘야함 / 귀찮으면 Ctrl + F2)

**사이드바 숨기기**

Hide / Show Sidebar: ⌘ + B or Ctrl + B

### ****2.8 Form Tags****

**form** 만들기

**input tag** = 입력창 만드는 태그

**input type** =’ “ input의 유형을 만드는 태그“ 

**input placeholder** = 무엇을 입력해야 하는지 안내하는 속성

**input value** = 입력 태그의 초기 값을 설정하는 속성

**required**  반드시 입력하라는 속성

**minlength** = “최소한의 글자를 입력해라”

form tag 설명 (기억 못해도 찾아서 사용할 수 있으면 가능)

HTML 문법 형식만 알아두기

### ****2.9 More Tags and IDs****

**label** 

 input과 함께 작동한다.

for과 같은 값을 가진 id를 들고있는 input을 작동시킨다.

**id**

body 어디안에 넣을 수 있는 attribute이다.

id값은 고유해야한다.

태그는 하나의 id만을 가질 수 있다.

### ****2.10 Semantic HTML****

**none-semantic** 

html에서 의미 없는 태그 but 기능은 있음. (div)

**semantic** 

문서를 보기만해도 그 의미를 짐작할 수 있는 것.

**div tag = division** (박스라고 생각해도 됨) 아무런 값이 없는 단순한 box

**header tag** = div 대체 태그 (head와 헷갈리지 않기. head는 보이지 않지만 header는 보인다)

**main tag** = 내용을 의미하는 태그

**footer tag** = 꼬릿말을 의미하는 태그

**span tag**= 짧은 텍스트를 의미하는 태그
