****3.2 What Does Cascading Mean****

브라우저가 CSS를 읽을 때 위에서부터 순서대로 읽는다.

CSS를 직접 적는 것을 inline CSS, CSS 파일을 include 하는 것을 external CSS라고 한다.

만약 같은 selector를 가리키는 CSS가 여러개이면, 가장 마지막 스타일이 적용된다.

****3.3 Blocks and Inlines****

div는 다른 div가 옆에 오지 못한다.

span은 다른 span이 옆에 올 수 있다.

**block**

옆에 다른 요소가 못 오는 것

**inline(in the same line)**

다른 요소가 올 수 있는 것

****3.4 Margin Part One****

inline요소는 너비와 높이를 가질 수 없다.

block요소는 너비와 높이가 있다.

box의 3가지 속성 

margin

box의 border의 경계에 바깥에 있는 공간이다.

margin-top: a;

margin-right: b;

margin-bottom: c;

margin-left: d;

border 

padding

3.5 ****Margin Part Two****

- **margin**
    
    방향 설정 없이 margin 하나를 주면 사방에 전부 다 적용된다.
    
    두 개를 줄 경우 상하, 좌우 이다.
    
    네 개를 줄 경우 시계방향 순으로 적용된다. (상 우 하 좌)
    
- **Collapsing margin 현상** (상하에서만 발생함)
    
    body안에 div의 위 아래 마진이 body의 마진과 만나면 둘 중 큰 값의 마진으로 body에 적용된다
    

****3.6 Paddings and IDs****

padding은 margin과 반대 개념이다.

padding은 경계 안쪽으로부터의 공간이다.

여러 div를 생성했을 때 'id'를 이용하여 div들을 구분할 수 있고, 각각 다른 속성을 적용시킬 수 있다.

CSS로 first div에 속성을 적용 시킬 땐, #first {}.

****3.7 Border****

border

 box의 경계이다.

 * 

 전체박스의 경계를 뜻한다.

border 

 굵기, 스타일, 색상 순이다.(2px, solid, color)

****3.8 Classes****

**inline요소**는 margin을 좌우로만 가질 수 있다. ( ex) span)

온점(.)은 class명이라는 뜻.

**#tomato = id="tomato"** 

**.tomato = class="tomato"**

- id명과 다르게 class명은 유일할 필요가 없다. 여러 요소들이 같이 쓸 수 있다.

class = “tomato hello honey”

- **class 속에는 btn과 tomato를 연이어 넣어** 각각 다른 class 속성을 동시에 부여할 수도 있다.

<span class="btn teal">Hello</span>
<span class="btn tomato">Hello</span>

사용이유

class는 여러 곳에서 사용가능하다.

중복된 코드를 하나로 만들 수 있다.

****3.9 Inline Block****

inline 

wdt, hgt 무시돼서 무언가 추가하지 않는 이상 아무것도 안보임

inline-block

block이 inline속성을 가지게해줌

반응형 디자인 지원되지 않음

block 사이에 공간이 지멋대로 생긴다

****반응형 웹 디자인****

 다양한 디바이스와 다양한 크기의 화면에서 일관되게 잘 작동하는 웹 페이지를 제작하는 일입니다****.****

****3.10 Flexbox Part One****

flexbox의 규칙

자식 엘리먼트에는 어떤 것도 적지 말아야한다. 자식 엘리먼트에 말하지 않고 부모 엘리먼트에만 말한다.

 justify-content : main axis에서 작용 (가로) (디폴트)

justify-content: flex-end

                         space-evenly

                         center

                         space-between

**align-items** 

cross axis에서 작용 (세로)

flex-container가 height를 가지고 있지 않으면 align-items: center; 을 사용하더라도 위치가 바뀌지 않음.

**vh = viewport height** 

화면 크기에 따라 다름

스크린에 따라 다름

****3.11 Flexbox Part Two****

**flex-direction**

main axis, cross axis의 기본 값을 바꾸기 위해서는 flex-direction을 사용한다.

flex-direction: column은 align-items를 가로로  

justify-content을 세로로 변경한다.

원하는 만큼 flex 컨테이너를 만들 수 있다.

**flex-wrap** 

 wrap로 설정하면 한 줄에 컨텐츠가 들어갈 수 있는 만큼만 보여주고 나머지는 다음 줄로 넘김.

no wrap일 경우 크기를 줄여서라도 한 줄로 표시

****3.12 Fixed**** 

position: fixed

새로운 layer를 만듦(기존과는 다른 layer에 content를 배치함)

position fixed를 이용하면 스크롤해도 항상 제자리에 머무른다.

처음 만들어진 자리에 고정되어 있다. 하지만 top,right,bottom,left중 하나만 수정해도 서로 다른 레이어에 위치하게 된다.

****3.13 Relative Absolute****

**position**

위치를 아주 조금 위,오른쪽, 등등으로 옮기고 싶을때 사용

**position: relative;**

element가 '처음 생성된 위치'를 기준점으로, top bottom left right으로 위치를 조금씩 수정할 수 있다. margin값을 생각한다.

**position: absolute;**

가장 가까운 relative 부모를 기준으로 이동한다.

position:relative; 를 해주면 부모가 된다.

없으면 body.

****3.14 Pseudo Selectors part One****

pseudo selector

좀더 세부적으로 엘리먼트를 선택해 주는 것

```python
div:first-child {
background-color: tomato;

}

/* pseudo selector */

div:last-child {

background-color: teal;

}
```

id나 class를 따로 만드는것보다 이렇게 지정하는게 훨씬 좋은 방법이다.

css에서만 선택을 하면 되니까! html코드를 고칠 필요가 없기 때문이다

n번째 태그 수정하기 nth-child(n) 올ㅋ

span:nth-child(2) {

background-color: teal;

}

span:nth-child(even) { //or odd ( 홀수 )

background-color: teal;

}

****3.15 Combinators****

p span 

p밑에 있는 모든 span이  효과를 가진다.

div > span

바로 밑의 자식만 효과를 가진다.

p + span 

+를 사용하면 형제에게 영향을 끼칠 수 있다.

동등한 위치의 span에게 영향을 미침

****3.16 Pseudo Selectors part Two****

"~"는 span이 p의 형제인데, 바로 뒤에 오지 않을 때 쓸 수 있다.

**Attribute selectors 특성 선택자**

그냥 input과 required input이 있다면, input:required{}를 통해서, required input에만 속성을 적용시킬 수 있다.

input{} 을 통해, [input 이름]에 해당하는 input 속성을 따로 줄 수 있다.

여기서, input[placeholder="First name"]은 First name에만 속성을 주지만,

**input[placeholder ~=”name”]**은 name을 가진 모든 속성에게 영향을 준다.

**input[placeholder *= “name”]**은 ㅇㅁㅇㄹnameㅁㅇㄹ라고 쳐도 선택된다.

****#3.17 States****

**active**

 해당 요소를 마우스로 클릭했을 때 효과를 적용

**hover** 

마우스가 해당 요소 위를 지나갈 때 효과를 적용

**focus** 

키보드로 선택되었을 때 효과를 적용

**focus-within** 

부모 요소에게 적용. 자신의 자식 요소 중 하나가 focused되었을 때 효과를 적용

**visited** 

방문한 사이트일 경우에 효과를 적용
