# [Memo] My Little knowledges

I'm going to just jot down some little knowledges that I got to know here to log.

# [HTML]
### `&nbsp;`
-> space를 의미

### table / rowspan & colspan
`rowspan`은 행을 병합 `coldspan`은 열을 병합
`<table>`의 attribute이다.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658791900240/SlD9NsNSk.png align="left")

# [CSS]

### flex
화면 정 중앙에 오게 하는 방법
```
background {
display: flex;
justify-content: center;
align-items: center;
height: 100vh;
}
```

### font
```
#title {
font-family: Georgia, "Times New Roman", Times, serif;
}
//주의) "Times New Roman"만 double quotes("")로 감싸져 있는데, 폰트 이름에 띄어쓰기가 되어있으면 사용해야함
```
### text-indent
```
p {
    text-indent: 30px;
}
// result => 들여쓰기
//         Hello everyone! recently I've been watching "Stranger things and it is so interesting and fun!"
```

### border
```
div {
      border: 2px solid red;
}
// border: width style colour; -> prefer to set in order like this as per coding convention(코딩규칙)
```
### background-size
```
div {background-size: 100%}
// 해당 배경 이미지가 div의 가로크기만큼 꽉 채워 그려주라는 의미
```

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658708113321/LSryQ_Kb1.png align="left")
css에서 `background`를 사용하여 이미지를 업로드 할 때, 유용하게 쓸 수 있는 사이즈 조절 property! 

### selector first-child / last-child
```
//html
<p>첫번째 paragraph</p>
<p>두번째 paragraph</p>
//css
p:first-child{color: red;}
p:last-child{color: blue;}
```
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658708787090/3HYlRaBKp.png align="left")

같은 selector가 여러개일 때, 첫번째 그리고 마지막번째를 위와 같이 선택하여 css를 꾸며줄 수 있다.

# [JavaScript]
### JavaScript setting
```
//JavaScript file을 HTML 에 연결 시켜줄 때, 아래와 같이 `<head>` tag 안에 defer와 함께 넣어주면 좋다.
<head>
<script defer src="app.js"></script>
</head>
```
```
//app.js -> 자바스크립트는 유연한 언어이기 때문에 자바스크립트 파일을 시작할 때 아래와 같이 입력 해 주면 좋다.
'use strict'
```