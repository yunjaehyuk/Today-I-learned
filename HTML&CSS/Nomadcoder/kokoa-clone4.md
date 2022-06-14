### 4 ADVANCED CSS

**4.0 Transitions**
 **transitions**
        
어떤 상태에서 다른 상태로의 “변화”를 애니메이션으로 만드는 방법이다.
        
state가 없는 요소에 붙여야한다.
        
바뀌는 것들에 한정해서 transition이 일어날 수 있다.
        
가장 처음 생겨난 곳에 있어야한다.
        

****4.1 Transitions part Two****

transition은 상태에 따라 바뀌는 요소가 있을 떄 사용 ex)hover, active, focus

ease-in-function: 브라우저에게 변화하는 방법을 알려줌.

linear, ease-in, ease-out, ease-in-out

**4.2** ****Transformations****

**transformation**

한 요소를 말 그대로 변형

다른 box element, 이미지에 영향을 끼치지 않는다.

margin,padding이 적용되지 않는다.

transformation은 box차원에서 일어나지 않고 결합이 가능하다.

****4.3 Animations part One****

**Animations**

@keyframes 애니메이션 이름{

from{
}

to{

}

}

img{

animation: 애니메이션 이름 재생시간 옵션

}

****4.4 Animations part Two****

from to 말고 0% 25% 50% 75%  100% 같이 여러 단계로 나누어 애니메이션을 만들 수 있다.

다른 property도 애니매이션으로 만들 수 있다.

****4.5 Media Queries****

**Media query**

 CSS만을 이용해서 스크린의 사이즈를 알 수 있는 방법이다.

핸드폰, 태블릿의 크기가 이 만큼이면 이 CSS를 보여줘

@media screen and (max-width:00px){}을 이용하여 몇 픽셀부터는 달라보이도록 만들 수 있다.

min사이즈와 max사이즈를 조절하여 단계별로 만들면, 스크린 사이즈의 범위를 알 수 있다.

media screen에 (orientation: landscape)를 이용하면, 세로모드인지 가로모드인지 알 수 있다.

****4.6 Media Queries Recap****

@media query는 코드의 조건을 추가할 수 있는 방법이다.

media query도 {} 중괄호로 여닫는다.

→ 그 안에 element에 속성을 적용시켜야한다.

media query는 “and”를 써서 연결된다.

@media print를 이용하면 브라우저 프린트 화면에서의 속성을 변경할 수 있다.
