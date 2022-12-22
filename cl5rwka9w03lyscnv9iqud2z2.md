# [CSS] position 속성 - relative, absolute, fixed

# position

position에는 화면 속 포지션을 지정해 줄 수 있는 요소들이 있다.
요소들 중에는 :
1. static - default
2. relative
3. fixed
4. absolute
5. sticky

가 있는데, 이 블로그에서는 relative, absolute 그리고 fixed를 중점적으로 알아볼 것이다.
위의 요소들을 이용하여 포지션을 지정해 줄 때, top, bottom, left 그리고 right 요소들을 사용할 수 있는데 이는 오직 position속성을 사용할 때만 이용 가능하다. 

## 1. relative

> An element with `position: relative;` is positioned relative to its normal position.
<br>출처 : w3schools

보통 포지션에 대한 상대적인 위치를 말한다.
요소 자기자신을 기준으로 배치한다.

Example :

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658217079616/x9Jamw-eH.png align="left")

## 2. absolute

> An element with position: absolute; is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed).

> However; if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling.

> Note: Absolute positioned elements are removed from the normal flow, and can overlap elements.
<br>출처 : w3schools

내가 position중에 제일 어렵다고 느끼는 absolute. 
정의를 읽어보면, 부모를 필요로 하는 자식의 느낌. 부모를 전체라고 생각하고 그 안에서의 포지셔닝을 말하는 것 같다.
jsbin으로 test를 진행 해 보았다.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658217681750/lKMytjMiS.png align="left")

직접 테스트를 해보니 감이 잡히는 것 같다. 처음엔 자식tag들에만 `position:absolute;`를 지정해 주었더니 red blue green끼리 스페이스도 겹치고 엉망이였다. 그러다가 미리 만들어놓은 부모tag에 `position:absolute;`를 지정했더니 자식tag들이 정신을 차리고 부모 tag아래에서 예쁘게 정렬되었다! 이제 뭔가 absolute를 잘 쓸 수 있을 것 같은 느낌이!! 

## 3. fixed

>An element with position: fixed; is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element. A fixed element does not leave a gap in the page where it would normally have been located.<br>
출처 : w3schools

제일 간단하면서 뭔가 한것처럼 보이는 fixed position! 
```
.fixed {
  position: fixed;
  bottom: 100px;
  background-color: aqua;
}
``` 

![fixed.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1658218458086/7xjdLzpsS.gif align="left")

위와 같이 코드 작성 후 화면을 보면 설정한 위치에서 움직이지 않고 스크롤 하는대로 따라가는 것을 볼 수 있다.
상단 메뉴 바 같은 것을 구현할 때 사용하면 유용할 것 같다.