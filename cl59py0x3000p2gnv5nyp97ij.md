# [CSS] Flexbox

간단한 HTML과 CSS를 이용하여 자기소개 웹사이트를 구현 해 보았다.<br>
*자기소개 Page->[https://suziech.github.io/wk01/](Link)*

이 웹사이트를 구현하며 가장 헤매었던 것은 메인페이지의 사진과 이모티콘 공간의 배치였다.<br>
position: absolute를 사용하니 사진과 이모티콘들이 자리를 못잡고 여기저기 정렬되지 않은 채 화면에 나타났다. 

어떻게 해야하지 고민하고 있었는데 같이 공부하는 팀원 중 한분께서 "Flexbox"를 사용해 보라고 하셨다.

바로 Flexbox를 공부하고 사용해 보았고, position으로 화면 정렬하는 것보다 훨씬 유용하고 쉬워서 메인페이지에 균형있게 잘 배치할 수 있었다.


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657100850576/hh7UvKdG4.png align="left")
> 내가 만든 웹사이트의 메인페이지 😵‍💫 Flexbox를 이용하여 사진과 이모티콘을 정렬시켰다.<br>
Layout이 잘 보이도록 선으로 표시했다.

# Flexbox란?

가로와 세로로 아이템을 배치해주기 위한 일차원적인 layout 방법이다. 아이템은 공간의 크기에 따라 줄어들거나 늘어난다. 이 기능을 쓰다 보면 여백이 일정하게 맞춰지는데 정말 신기하다. 과거에는 CSS에 layout을 설정 해 주기 위해 floats이나 position features를 이용했지만, 이 기능엔 한계가 있었기에 Flexbox feature가 생긴 것 같다. 

# Flexbox 사용방법


![Screenshot 2022-07-06 at 6.47.14 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657102162831/gzpFQG80A.png align="left")

> 위의 그림에 보이는 것 처럼, Flexbox로 item을 감싸고 그 item들을 크게 또 감싸는 형식으로 진행했다.
1번을 아래 위로 정렬, 그리고 2번을 가로로 정렬하는 식.

*1. `<div>`에 class를 설정한다

```
         <div class="flexbox-container">
            
             <div class="column">
                <div class="main_pic"></div>
              </div>
               <div class="row">
                <div class="menu"><a href="introduction.html" title="Introduction">👋</a></div>
                <div class="menu"><a href="travel.html" title="Travel">✈️</a></div>
                <div class="menu"><a href="hobbies.html" title="Hobbies">🤸‍♀️</a></div>
                <div class="menu"><a href="me_now.html" title="My new challenge">🚀</a></div>
            </div>       
        </div>
``` 
> HTML 메인 페이지 이다. 첫번 째 (아래-위)로 나눌 `<div>`에 "flexbox-container"라는 class를 주었고, 두번 째(가로)로 나눌 `<div>`에 "row" 로 class를 설정해 주었다.

*2. 설정한 class에 display:flex;를  적용한다.

```
.flexbox-container {
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    align-items: center;
    align-content: space-around;
}

.row {
    display:flex;
    flex-direction: row;
    justify-content: space-around;
    flex-wrap: wrap;
}
``` 
> `display: flex;`를 각 class에 설정해 주고, 원하는 방향에 따라 flex의 property와 value를 작성해 주면 된다.

# Flexbox를 이해하기 위해 도움이 되었던 자료들

Flexbox를 이해하기 위해 도움이 되는 게임과 영상을 아래에 추천한다.

- 개구리게임 🐸 : https://flexboxfroggy.com/
- 드림코딩 🌈 : https://www.youtube.com/watch?v=7neASrWEFEM




