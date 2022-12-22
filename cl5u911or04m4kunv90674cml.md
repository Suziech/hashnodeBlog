# [CSS] <link type="text/css"/>

CSS를 external file로 사용할 경우, html `<head>`tag안에 link를 넣어 연결 시켜 주어야 한다.

이제까지 내가 썼던 링크는 아래와 같다.

```
<link rel = "stylesheet" href = "style.css">
``` 

하지만 공부하다보니 처음보는 속성이 보였다!

```
<link href="style.css" rel="stylesheet" type="text/css" />
``` 
부연설명 
- link : link tag로 사용할 CSS file을 link 해 줌
- href : 이 attribute에 css file route 작성
- type : link tag 로 연결되는 file이 어떤 것인지 알려줌. 여기서 css file을 연결하므로 type값은 항상 "text/css"
- rel : rel은 html file과 css file의 relation을 설명하는 attribute. css file을 링크할때 항상 "stylesheet"값 대입

바로 이 맨 끝에 있는 type="text/css"/

으잉?!?! 이게 뭐지!?!? 바로 조사에 착수.

알고보니 사실 별거 아니였고 예전 버전의 html을 사용할 때 넣어 주던 속성이였다.
html5부터는 사용하지 않아도 별 문제가 없다고 한다.

이 전에 type을 써 주었던 이유는 MIME type의 속성을 주기 위해서라고 하는데 또 처음들어보는 MIME type.

> MIME 이란?<br> Multipurpose Internet Mail Extensions의 약자로 파일 변환을 말한다.
text file로 변환된것을 인코딩 하기 위해 사용한 걸로 보인다.


참고 : [https://stackoverflow.com/questions/5409114/is-type-text-css-necessary-in-a-link-tag](Link)

👩‍💻 결론 : html5를 쓰고 있어서 신경써도 되지 않을 부분이지만 그냥 나처럼 궁금해 하실 분들을 위해 블로그를 작성 해 보았다.

끗.