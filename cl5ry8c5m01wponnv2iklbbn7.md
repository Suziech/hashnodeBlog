# [HTML/CSS] Layout : inline, block, inline-block 에 대해서

inline, inline-block, block
셋 다 다른 요소들이지만 이름이 비슷해서 헷갈릴 수 있으니 한 번 정리 해 보겠다.

일단 block 과 inline을 먼저 알아보겠다.

모든 HTML elements들은 어떤 타입의 요소인지에 따라 default display value가 설정 되어있다.
그리고 거기엔 2가지 display value가 존재한다 : block & inline.

# 1. inline

>  An inline element does not start on a new line. An inline element only takes up as much width as necessary.<br>출처: w3schools

w3schools에서 정의한 것과 같이 inline element는 여러개를 사용하게 되면 새로 줄바꿈은 없다(content 크기 만큼의 width를 차지하기 때문).

e.i. `<span>`을 사용하면 줄이 바뀌지 않고, 한 줄에 이어서 나오게 된다. 이렇게 한 줄에 이어서 나오는 요소를 inline-element라고 한다.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658219696821/bQdZnxsJM.png align="left")

아래는 inline elements의 종류이다.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658219819517/DYEEF30MP.png align="left")

그리고 `display: inline;` 를 사용하게 되면, block이 default인 element를 inline으로 변경 가능하다.


# 2. block

>A block-level element always starts on a new line, and the browsers automatically add some space (a margin) before and after the element.<br>출처: w3schools

block은 inline과 다르게 line을 다 차지해서 rendering해서 확인 해 보면 새로 줄바꿈이 된다.
가장 많이 사용하는 block element로는 `<p>` 와 `<div>`가 있다.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658220063549/lq_LfkxFH.png align="left")

그리고 `display: block;` 를 사용하게 되면, inline이 default인 element를 block으로 변경 가능하다.

# 3. inline-block

자, 이제 CSS의 layout인 그리고 오늘 블로그의 주인공 같은 `inline-block`에 대해 알아보자.

`display: inline;`과 가장 다른 점을 찾는다면, `display: inline-block;`은 element의 가로 세로 길이를 설정 해 줄 수 있는 것이다. 또한 top, bottom, margins, paddings도 설정이 가능하다.

`display: block;`과 비교해보면, line-break(줄바꿈)기능이 없어 다른 요소 옆에 render가 가능하다.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658221316017/rk-rLSP7e.png align="left")

오 역시 블로그로 정리를 해보니 대충 알긴 알았던 지식들이 머리속에서 정리가 되는 기분이다. 
기술블로그의 중요성이 몸소 느껴진다! 