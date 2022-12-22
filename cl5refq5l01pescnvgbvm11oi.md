# [HTML] Viewport  in <meta>

# Viewport란?

Viewport란 웹페이지에서 사용자에게 보여지는 부분이다. 사용자가 스마트폰을 사용하는지 또는 데스크탑을 사용하는지에 따라 화면의 크기가 달라지게 되는데, 이 달라지는 화면의 비율에 따라 웹페이지의 크기를 조절 해 주어야 한다.

HTML5에서는 `<meta>`안에 viewpoint 요소를 설정할 수 있다.
```
<meta name="viewport" content="width=device-width">
```
위의 코드를 입력하게 되면, 브라우저에게 어떻게 크기를 조절해야 하는지 instruction을 준다.

👩‍💻 Today I learnt : 

`<head>`안에 viewport를 설정해주어야 하는 것을 알게 되었다!
viewport를 설정해주는 태그에 `content="width=device-width`는 말 그대로 디바이스의 가로 크기가 곧 웹 페이지의 가로 크기와 같다는 의미이다. 이 정보를 추가하지 않으면 웹페이지가 축소되어 보인다고 한다.

더 자세한 정보 :
[https://www.w3schools.com/css/css_rwd_viewport.asp](Link)

직접 내 자기소개 페이지에 설정 해 보았다.

설정 전:

![IMG_2904.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1658188067328/2GKZvMDBt.PNG align="left")

설정 후:

![IMG_2905.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1658188091461/yG0P84pmc.PNG align="left")

화면이 모바일 사이즈로 커진건 커졌는데.. 흠.. 왜 화면이 제대로 중앙에 오지 않을까? 연구 해 봐야겠다.