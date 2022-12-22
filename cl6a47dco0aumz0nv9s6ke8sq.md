# [React] Intro

## React의 등장
### 1. Web Application의 발전

- React는 어떤 문제를 해결하기 위해 만들어진 기술인가?

   ➡️ 과거에는 단순했던 Web Application이 점점 동적이고 유저와의 상호작용이 많아지면서 다루어야할 data와 code가 증가하였다. 이 상황에서 DOM으로 접근해서 조작했던 방법으로는 개발 그리고 유지,보수가 어려워지게 되었다. 이런 상황으로 인해 React와 같은 다양한 Framework와 Library가 등장하게 되었다.
- Web Application 이란?

   ➡️ 사용자가 별도로 응용 소프트웨어(Application)을 설치하지 않아도 웹 브라우저를 통해 기능을 이용할 수 있는 웹 서비스이다. ex) 문서작성, 쇼핑, SNS, 게임 in Web browser.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659267918550/gTu9ihjoW.png align="left")


### 2. Framework와 Library

   🔹 공통점
   
   Framework와 Library는 복잡하고 고도화된 개발을 효율적으로 그리고 편리하게 하기 위해 개발자들이 만들어 둔 코드이다.
   
   🔸 차이점
   
   ➡️ Framework : 다른 사람이 만들어 둔 코드의 정해진 틀(Frame) 속에서 수동적으로 작업(work)해야한다.(e.g.)Angular, Vue)
   
   ➡️ Library : 개발자가 필요한 기능이 있으면 찾고(Library) 능동적으로 가져와 사용 가능하다.(React -> framework 적인 특징 일부를 갖고있긴 함)

❓ React가 가지고 있는 framework 적인 특징은 무엇인가?


### 3. React를 사용하는 이유

   ➡️ React는 대부분 JavaScript문법을 그대로 활용함. 그러므로 접근성이 좋다.\
   ➡️ Facebook의 지속적인 관리와 함께 eco-system이 활성화되어있어 user가 많고 community가 발달해 있다.\
   ➡️ React 기반의 React Native라는 기술을 통해 웹 as well as IOS, Android 기반 mobile application도 개발 가능

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659267995644/kwy99-PjS.png align="left")

# React의 정의 & 특징

## 1. React의 정의

   ➡️ React는 Facebook에서 개발하고 관리하는 UI를 만들기 위한 JavaScript Library이다.
   ➡️ React를 사용하는 가장 큰 이유 : UI 자동 update 해줌
   - 자동업데이트로 인해 아래와 같은 이점이 있음:
   1. data기반의 선언적 개발 가능
   2. 자동으로 UI를 업데이트 하는 과정에서 virtual DOM을 통해 최적화된 업데이트 가능
   3. Component기반의 개발을 통해 복잡한 UI를 효과적으로 구성가능
   4. JSX문법으로 Component 편리하게 작성 가능

❓ 여기서 말하는 virtual DOM(가상 돔) 이란 react JSX에서 쓰는 html 을 말하는 건가?


## 2. React의 특징

   ### 🔹 선언적
   개발은 절차적(명령적) How to solve? / 선언적 방식 What to solve? 으로 나뉘어짐
  
  예시 : 

🚖 절차적 : 이 방향으로 직진해서 두 번째 블록에서 우회전해주시고, 이후 첫 번째 신호등에서 좌회전해주세요. 전방에 다리를 건널 때까지 직진해주시고, 소방서가 있는 블록에서 우회전 후 300m 앞에서 내려주세요. (How to solve?)

🚖 선언적 : OOO으로 가주세요. (What to solve?)

   ➡️ JavaScript : 절차적
   ➡️ React : 선언적 -> React가 절차적인 방식을 알아서 처리해줌.

   ### 🔹 Virtual DOM (가상 돔)
   
   React에서 UI를 update 할 때, virtual DOM을 이용해 실제 DOM에 일어나는 변화를 계산함.\
   Why??\
   화면이 변할 때 마다 매번 DOM - layout계산 - paint 을 수백, 수천개의 요소에 하게되면 성능 저하, 프로세스 비 효율적이됨.
   
   ➡️ 이 문제를 해결하기 위해 virtual DOM을 통해 변경될 UI 최소 집합을 계산하여 DOM처리 최소화하고 효율적으로 진행(변하는 부분만 update 시킴)


   ### 🔹 Component
   
   What is Component?\
   ➡️ 재활용 가능한 UI 구성단위 (다른 기능의 구성단위를 모아 새로운것을 create할 수 있음)
   
   특징?\
   ➡️ 필요한 곳에서 재사용 가능\
   ➡️ 독립적 사용이 가능해 코드의 유지보수에 좋음\
   ➡️ 다른 component포함 가능 (parent - child)\
   ➡️ 해당 페이지가 어떻게 구성되어 있는지 한눈에 파악하기 좋음

   종류?\
   ➡️ Class Component 
   ```
   // App.js

import React from 'react';

class App extends React.Component {
  render() {
    return <h1>This is Class Component!</h1>;
  }
}

export default App;
   ```
   
   ✔️ class component에서는 위와 같이 *반드시* `render()` method가 있어야함\
   ✔️ 그 안에서 화면에 보여줄 JSX(JavaScript Syntax eXtension) 반환\
   ✔️ state & lifecycle API를 통해 관련기능 사용가능
   
   
   ➡️ Function Component
   ```
   // App.js

import React from 'react';

const App = () => {
  return <h1>This is Function Component!</h1>;
};

export default App;
   ```
   
   ✔️ `render()` method없이 JSX을 반환하는 방식\
   ✔️ 장점 : class보다 단순하고 간단함 / 단점 : state, lifecycle 관리 못함\
   ✔️ Hook기능 추가로 위의 단점 cover! -> state 사용이 가능해 지자 많이 사용되기 시작.
   
   
   How to use?\
   ➡️ 첫글자는 무조건 대문자 (e.i)<Welcome />)\
   ➡️ 선언된 component는 다른곳에 import하여 사용가능
   
### 🔹 JSX

   JSX의 정의\
   ➡️ JSX(JavaScript Syntax eXtension)이란 react에서 사용하는 javascript확장 문법\
   ➡️ JSX로 작성한 코드는 브라우저에서 동작하기 전에 Babel에서 transcomplier를 통해 vanilla JavaScript코드 형태로 변환해줌
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1659316471092/3ai3owbxH.png align="left")
- 위의 사진과 같이 변환됨 /(위) jsx로 작성한 코드 /(아래) babel로 변환된 JSX코드


   JSX의 특징\
   ➡️ HTML과 유사한 형태로 보기 쉽고 익숙함
   ➡️ 하나의 Javascript file에서 HTML 마크업과 자바스크립트 로직을 동시에 작성 가능해 편리함
   
   
   JSX 문법
   
   1. JSX element

   JSX문법을 통해 JavaScript파일 어디에서나 필요한 곳에 HTML처럼 작성 가능
```
const hi = <p>Hi</p>;
```

   2. Javascript 표현식

   JSX 내부에서 JavaScript값을 출력하고 싶으면 {...JavaScript...} 로 표현가능

```
// Greetings.js
import React from 'react';

const Greetings = () => {
  const name = '김개발';

  return <h1>{name}님, Welcome to Wecode!</h1>;
};

export default Greetings;
```

   3. JSX attribute
   
   attribute name(속성명)은 camelCase로 작성해야함
   class를 주고싶을 때, 원래 attribute name은 class지만 JSX에서는 className을 사용해야함


```
// HTML
<h1 class="greetings">Welcome to Wecode!</h1>

// JSX
<h1 className="greetings">Welcome to Wecode!</h1>
```

   4. Event 처리하기

   vanilla JS에서는 DOM element에 Event Listener를 부착하는 방식으로 event를 처리했지만, JSX에서는 tag작성시 직접 Event 와 Event Handler를 부여할 수 있음 

- 이벤트는 앞에 on을 붙여 camelCase로 작성
- 문자열이 아닌 함수로 이벤트 핸들러를 전달 ❓

```
// JS
const title = document.getElementsByClassName("title")[0];
title.addEventListener("click", handleClick);

// JSX
<h1 className="title" onClick={handleClick}>
  Welcome to Wecode!
</h1>
```

   5. Inline Styling

   Style속성은 HTML에서 문자열로 받는 것과 달리 camelCase를 요소로 가지는 JavaScript를 객체로 받음
   
   그러므로 `{{style attirbute}}` <- 이렇게 써야함 
   - 바깥의 { } 는 JSX 문법
   - 안쪽의 { } 는 JavaScript object를 의미

```
// HTML
<h1 style="color:red;background-image:yellow">Welcome to Wecode!</h1>

// JSX
<h1 style={{ color: "red", backgroundImage: "yellow" }}>
  Welcome to Wecode!
</h1>
```
(style 속성을 사용하는 inline styling은 css보다 성능이 낮고❓ 우선순위가 높기 때문에, 동적으로 계산하여 스타일링하는 경우 이외에는 사용을 지양하는 것이 좋다.)


   6. Self-Closing Tag

<img /> <div /> <p />
단일 tag사용시 항상 /로 끝마침을 해주어야 함



7. Nested JSX

반드시 최상위를 감싸고 있는 하나의 태그가 있어야 함

```
// Bad
const Greetings = () => {
  return (
    <h1>김개발님!</h1>
    <h2>위코드에 오신 걸 환영합니다!</h2>
  );
}

// Good
const Greetings = () => {
  return (
    <div>
      <h1>김개발님!</h1>
      <h2>위코드에 오신 걸 환영합니다!</h2>
    </div>
  );
}
```

- JSX를 하나의 태그로 감싸야 하는 이유는, 리액트의 Virtual DOM에서 컴포넌트 변화를 효율적으로 비교할 수 있도록 한 컴포넌트는 하나의 DOM 트리 구조로 이루어져야 한다는 규칙이 있기 때문


   8. React.Fragment

	- 최상위 tag에 의미나 스타일이 없는 경우 <React.Fragment> 사용 가능.
    - 추가적인 DOM element를 생성하지 않고 하나의 component안에 여러 child를 간단히 그룹화 할 수 있는 기능\



```
const Greetings = () => {
  return (
    <React.Fragment>
      <h1>김개발님!</h1>
      <h2>위코드에 오신 걸 환영합니다!</h2>
    </React.Fragment>
  );
};
```
축약형인 `<> ... </>` 문법으로도 동일하게 사용할 수 있습니다.
```
const Greetings = () => {
  return (
    <>
      <h1>김개발님!</h1>
      <h2>위코드에 오신 걸 환영합니다!</h2>
    </>
  );
};
```

# Node.js & npm

## 1. Node.js & npm

### Node.js

- JavaScript가 browser밖에서도 동작하게 하는 javascript 실행환경 (javascript의 "탈 웹")
- React Application은 web browser에서 실행되기 때문에 Node.js와 직접적 연관을 없지만, React 이 외에 project를 개발하는데 필요한 주요 도구들(e.g. Babel, Webpack, etc)은 웹 브라우저가 아닌 우리의 작업 환경에서동작해야 하기 때문에 반드시 Node.js를 설치해야함.

### npm

- npm(node package manager) : node.js를 install하면 자동으로 install됨.
- package란 node.js 환경에서 실행할 수 있는 프로그램을 뜻하며 npm을 통해 개발에 필요한 다양한 패키지를 설치하고 버전관리 가능
- 스마트폰에 비교하면 node.js는 ios, npm은 appstore로 표현 가능

# CRA

## CRA란?
- React는 UI기능만 제공 -> web application을 만드는 데 필요한 개발환경을 직접 구축해야할 것이 많음
- 이러한 문제 해결을 위해 React팀에서 React환경구축을 세팅해 주는 도구 (toolchain)인 CRA(Create React App)을 만듦

### CRA를 통한 project 구축

- 폴더 진입
```
$ cd [프로젝트를 구축하고자 하는 폴더]
```
- project install
```
$ npx create-react-app [프로젝트명]
```
- project folder 진입
```
$ cd [프로젝트명]
```
- local server 띄우기
```
$ npm start
```
- local server 확인
http://localhost:3000 이라는 로컬 서버주소를 확인

### CRA 초기세팅

- CRA초기 폴더 및 파일 구성
- node_modules, .gitignore, package.json
- index.html, index.js, App.js
- README.md

# 📍Summary

React는 DOM(Document Object Model)을 직접 조작하는 방식에서 벗어나 현대 web frontend 개발에 가장 많이 사용되고 있는 Library이다.\

- 어떠한 흐름으로 오늘날 `React`가 많이 사용되고 있을까?\

   공부 전 ➡️ React는 세계적인 기업인 Facebook에서 library로 출시하였고 library인 특징 답게 자신의 코드에 쉽게 적용이 가능해서 최근 제일 많이 사용하는 것 같다.\
   
   공부 후 ✅ JavaScript의 문법을 기반으로 이용이 가능해서 초보자도 접근이 쉽고 Facebook의 지속적인 관리와 eco-system이 활성화 되어있어 user가 많고 community가 발달 해 있음. 또한 React Native를 활용하여 IOS, Androd 등 mobile application 도 개발 가능하다\

- `React`란?\

   공부 전 ➡️ React란 facebook에서 출시한 library로 Vanilla JavaScript를 좀 더 쉽게 사용할 수 있게 해준다.\
   
   공부 후 ✅ Framework 특정을 약간 가지고 있는 JavaScript Library로 볼 수 있다. 능동적으로 필요한 기능을 가져다가 사용이 가능하다. Facebook에서 출시했으며 많은 User들이 세상에 존재한다.\
   
- `Component`의 개념과 종류\

   공부 전 ➡️ 함수와 같다고 볼 수 이다. 기능을 저장해 놓아 간단한 명령어로 사용할 수 있고, 재사용이 가능하다.\
   공부 후 ✅ component에는 2가지 종류가 있다. class 와 function. 최근 function 에 state를 사용할 수 있게 되면서 거의 사용하기 간단한 function을 사용하는 추세이다. component에는 기능을 저장할 수 있으며 재 사용이 가능하다.\
   
- `JSX`에 대한 정의와 기본 특성\

   공부 전 ➡️ 복잡한 'vanilla JavaScript'를 html구조를 이용하여 쉽게 사용할 수 있다 (파파고 통역기처럼 html언어를 javascript언어로 변환해 준다)\
   공부 후 ✅ 'JSX'란 JavaScript Syntax eXtention의 약자로, 자바스크립트 안에서 html 구문을 사용 가능하고 이를 babel을 통해 transcomplie시켜 다시 javascript 언어로 변환시켜 실행할 수 있게 하는 Javascript 문법이다. html과 유사하기 때문에 처음 접했을 때 사용이 쉽고 간편하다.\
   
- `CRA`는 폴더와 파일이 어떻게 구성되어 있을까?\

   공부 전 ➡️ CRA는 뭔지 잘 모르겠다.\
   공부 후 ✅ CRA란 Create React App 초기세팅의 어려움으로 인해 react팀에서 초기세팅을 도와주는 toolchain 만들어 줌.