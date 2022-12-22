# [CS]Semantic Web & Semantic Tag

# WEB 3.0 = Semantic Web!

> "사이트에 이미지를 넣는 방법은 두 가지가 있습니다. `<img>` 태그를 사용하는 것과 `<div>` 태그에 background-image 속성을 추가하는 것. 두 가지 방법의 차이점과 각각 어떠한 경우에 사용하면 좋은지 설명해보세요."

만약 위의 질문을 받게 된다면, 먼저 **Semantic Web & Tag**에 대한 이해가 있어야 한다.

>Semantic : relating to meaning in language or logic. / 의미의, 의미론적의

사전에 나온 뜻과 같이 Semantic Web & Tag는 의미있는 웹과 태그라고 설명할 수 있다.

더 자세히 알아보면, 

>The Semantic Web, sometimes known as Web 3.0 (not to be confused with Web3), is an extension of the World Wide Web through standards[1] set by the World Wide Web Consortium (W3C). *The goal of the Semantic Web is to make Internet data machine-readable.*(출처: wikipedia)
**

쉽게 말해, Semantic Web & Tag란 인터넷 데이터를 읽을 수 있게 만드는 것이 목표라고 할 수 있다.

Semantic web (= Web 3.0)은 한마디로 인공지능웹으로 볼 수 있다. 사용자가 입력한 단어 혹은 문장의 의미를 파악하고 분석하여 다양한 정보를 제공해주기 때문이다.

//<br>
아래는 web 1.0부터 3.0의 특징에 대한 설명이다.

*web 1.0 = 읽기전용*

*web 2.0 = 참여형 (facebook / instagram 등등), 컨텐츠 제작, 플랫폼중심*

*문제점 : 플랫폼의 힘이 너무 커짐 / 개인정보 유출 / 가짜뉴스*

*web 3.0 = 블록체인(탈 중앙화) / 창작자중심*<br>
//

Semantic Elements(Tags)에 대한 설명은 아래의 웹사이트에서 더 자세히 볼 수 있다. 
[https://www.w3schools.com/html/html5_semantic_elements.asp](Link)

A semantic element clearly describes its meaning to both the browser and the developer.<br>
Examples of non-semantic elements: `<div>` and `<span>` - Tells nothing about its content.<br>
Examples of semantic elements: `<form>`, `<table>`, and `<article>` - Clearly defines its content.

위의 설명으로 쉽게 이해 할 수 있는데, `<div>`나 `<span>` 같은 경우, 처음 보자마자 저게 무슨 역할을 하는지 전혀 감이 오지 않는다. 하지만 `<form><table>` 또는 `<article>`을 보면 평소에 사용하는 단어라서 자세히는 모르더라도 대충 어떤 용도로 사용될 지 느낌이 온다. 이렇게 인간친화적인 용어를 사용하는것을 semantic이라고 표현한다.

이제 의미를 알았으니 일전에 mention했던 질문에 답을 해보자.

`<img>` 태그를 사용하는 것<br>
better to use if:
- (alt 속성과 같이 사용) 이미지에 중요한 의미(semantic)가 들어있을 경우,(예를 들어 경고 아이콘 이미지), img 태그를 사용하면 screen reader포함, 전 사용자와 소통할 수 있다.
- background-image대신 img를 사용하면 배경에서 에니메이션 성능을 크게 향상 시킬 수 있다.<br>

`<div>` 태그에 background-image 속성을 추가하는 것<br>
better to use if:
- 이미지가 컨텐츠와 관련 없는 경우

> 결론 : semantic의 의미 그대로, web과 더 나은 communication을 위해 `<img>` tag를 사용하면 SEO(Search Engine Optimisation)향상에 도움이 되는 등, 좀 더 나은 웹 환경을 구축할 수 있다. 특히 이미지가 컨텐츠와 관련이 있는 경우!
하지만 이미지가 컨텐츠와 관련이 없다면 background-image속성을 이용해도 괜찮다.

