# [CSS] Add gradation effect to your text!

[👉 linear-gradient() MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient)

# 글씨에 그라데이션 효과넣기 방법! 
1. 일단 예시로 `<h1>` tag를 사용하여 글씨를 작성
2. CSS에 상위에 `background`속성에 `linear-gradient`를 써주고 그라데이션 방향(to right)을 써준 후 원하는색깔을 넣어준다. 
3. `-webkit-background-clip: text;`을 추가! 이 부분이 바로 글씨에 색깔을 넣어줄 수 있다! 
4. `color: transparent;`를 추가로 넣어준다. 
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1669274053950/u7ttT193u.png align="left")

```html
<!--html-->
<h1>안녕하세요! 만나서 반갑습니다. 신기하네요!</h1>
```
```css
/*css*/
h1 {
    background:linear-gradient(
      to right,
      red,
      orange,
      yellow,
      green,
      blue,
      indigo,
      purple
    );
-webkit-background-clip: text;
  color: transparent;

}
```
> 오오 너무 신기해! CSS는 이런게 정말 재미있는듯 🤓